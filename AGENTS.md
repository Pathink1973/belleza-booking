# Project Architecture Rules

- Register the service worker only in production and never cache Vite source or dependency-module URLs, because stale development modules can load multiple incompatible React runtimes.