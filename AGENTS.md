# Project Architecture Rules

- No app-shell service worker: public/sw.js is a kill-switch that unregisters itself, because the old offline worker broke page loads (failed navigations, stale React modules).
