# Hardware Manager Demo Plan
1. **Initialize Project**: Use the `fabrica_init` MCP tool on the `fabrica` MCP server. to create `hardware-manager`.
   - Enable metrics, events, and reconciliation.
   - Use absolute path: /Users/ben.mcdonald/demo-fabrica/hardware-manager
   - The `working_dir` parameter MUST change after Step 1. Step 1 uses the parent directory. Steps 3 and 4 MUST use the newly created `hardware-manager` subdirectory.
2. **Add Resource**: Use the MCP tool to add a `Device` resource with fields `serial_number`, `device_type`, `redfish_uri` in Spec and `parent` in Status. You don't need to specify a version.
3. **Generate**: Use the `fabrica_generate` MCP tool and run `go mod tidy`.
4. **Implement**: Use patterns in `docs/reconciliation.md` to update `Status.Parent` based on `Spec.RedfishURI`.
5. **Verify**: Follow the test plan in `VERIFY.md`.