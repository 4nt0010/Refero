# Decimen Optical Transfer: fountain-coded QR file transfer

Send a file between two devices using nothing but a **screen and a camera**.
One page displays the file as an endless stream of animated QR codes; another
device points its camera at it and reconstructs the file. **No network path
between the devices, no app, no pairing, no permissions beyond the camera.**
The payload travels as light.

## Try it

```bash
npm install
npm run dev
```

- On the **sending** device (a laptop is ideal): open
  `https://localhost:5173/send/` and it starts streaming immediately. Max
  screen brightness helps.
- On the **receiving** device (a phone): open the `Network` URL Vite prints
  (`https://<lan-ip>:5173/receive/`), accept the certificate warning once,
  tap **Start camera**, and point it at the code.
- A few seconds later: *Transfer Complete!* and the received image, verified
  by hash.

**Why the dev server is https-only:** the receiver uses `getUserMedia`, and
browsers remove that API entirely on insecure origins. The dev server ships
with a self-signed certificate; tap "Show Details" then "visit this website"
(iOS) or "Advanced" then "Proceed" (Android/desktop).

Hold the phone steady, or better, prop it against something. Camera
autofocus hunting from hand tremor is the #1 throughput killer.

## License

MIT
