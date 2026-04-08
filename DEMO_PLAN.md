# Hardware Manager Demo Plan
1. **Initialize**: Project `hardware-manager` in the current folder. 
   - Enable metrics, events, and reconciliation.
   - Use absolute path: /Users/ben.mcdonald/demo-fabrica/hardware-manager
2. **Add Resource**: `Device` with fields `serial_number`, `device_type`, `redfish_uri` in Spec.
3. **Generate**: Run `fabrica generate`, then `go mod tidy`.
4. **Implement**: Use patterns in `docs/reconciliation.md` to update `Status.Parent` based on `Spec.RedfishURI`.
5. **Verify**: Follow the test plan in `VERIFY.md`.