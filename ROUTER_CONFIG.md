# Router config

I have a AX5400 Wi-Fi 6 Router which is accessible on http://192.168.0.1/

- password: `.env`

## Port forwarding

I forwarded ports 22, 3000, 80 and 443. For example for SSH port forwarding I did the following settings.

- WAN port - 2222
- LAN port - 22
- Destination IP - Raspberry Pi

Test if port forwarding is correctly configured - https://www.yougetsignal.com/tools/open-ports/. If nothing is running on the port, it will report it as closed (even if it's not!).
