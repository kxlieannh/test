Use these filters to see where bad logins are coming from:

1. Kerberos (main AD login)
kerberos
kerberos.KRB_ERROR

2. NTLM (fallback login method)
ntlmssp
ntlmssp.auth

3. LDAP / LDAPS (services, apps, printers authenticating)
ldap
ldap.bindRequest
ldap.bindResponse.resultCode != 0

4. SMB (mapped network drives causing lockouts)
smb2
smb2.nt_status == 0xc000006d

5. RPC / Netlogon (Windows services, scheduled tasks)
rpc
dcerpc
netlogon

6. DNS (devices looking for a Domain Controller)
dns && dns.qry.name contains "ldap"

7. RDP (Remote Desktop bad logins)
tcp.port == 3389 and ntlmssp.auth

8. VPN / RADIUS (VPN login failures)
radius
eap

9. Exchange / Mobile Email Apps
tcp.port == 443 and http contains "ActiveSync"

10. Legacy / Old Devices
browser
nbns
cifs

All-In-One Filter (use this if unsure)

This shows almost everything related to AD authentication:

kerberos or ntlmssp or ldap or smb2 or rpc or dcerpc or netlogon or radius or eap or cifs or browser

What To Look For

Pick a failed authentication packet.

Look at the Source IP → this is the device causing the lockout.

Expand the protocol layer to see the username being used.
