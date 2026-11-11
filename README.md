# selfie

Camera test app for the Nokia N900 (Maemo 5): live preview of the front or back
camera and a shutter button. Python 3 + [hildonlite](https://github.com/n900-resurrection/hildonlite),
GStreamer 0.10 `camerabin` with `libomap3cam` (correct white balance).

- Switch between front (`/dev/video1`) and back (`/dev/video0`) camera.
- Photos go to `~/MyDocs/DCIM/selfie-YYYYMMDD-HHMMSS.jpg`.
- Hardware camera button half-press takes a photo (`SELFIE_BUTTON`, default `cam_focus`).
  A full press launches the stock Camera app and cannot be intercepted.
- `SELFIE_DRIVER` overrides the camera source driver (default `libomap3cam.so.0`).

## Build

Inside the N900 repository (uses `mk/app.mk`):

    make -C apps/selfie deb

Depends on `python3.11`, `python3-hildonlite`, `gstreamer0.10-plugins-camera`, `libomap3cam`.
`make-icon.sh` regenerates the icons.
