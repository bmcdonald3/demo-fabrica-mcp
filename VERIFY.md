# Verification Steps
1. Start the server: `go run ./cmd/server/` (run in background).
2. Create a Blade: 
   ```bash
   curl -X POST http://localhost:8080/devices -d '{
     "spec": {
       "serial_number": "ABC-123",
       "device_type": "Blade",
       "redfish_uri": "/redfish/v1/Chassis/RackA/Blades/Blade1"
     }
   }'
   ```
3. Check Reconciliation:
    ```bash
    curl http://localhost:8080/devices/ABC-123
    ```
Success Criteria: The status field should now contain "parent": "RackA".