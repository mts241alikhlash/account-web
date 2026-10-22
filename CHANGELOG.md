# account-web

## 1.2.4

### Patch Changes

- d087eea: Run on Node.js 24.22.1, the release that fixes the October 2026 security issues (Brotli decoder out-of-bounds write, TLS hostname checks, DNS NUL handling). The base image, the CI jobs and the engines range move from 24.21.0 to 24.22.1.

## 1.2.3

### Patch Changes

- e8e48aa: Ejaan Amerika di kode, komentar, dan nama test (`honours` menjadi `honors`, `enrolment` menjadi `enrollment`, dan sejenisnya).

## 1.2.2

### Patch Changes

- a9da878: Field profil, alamat, dan ubah password memakai `FloatingField`; header card memakai standar `@mts241alikhlash/ui` 1.8.

## 1.2.1

### Patch Changes

- cf311ca: The profile identity tab uses floating-label fields like the other apps.

## 1.2.0

### Minor Changes

- ae55564: The profile address editor now selects official administrative regions and saves their codes.

### Patch Changes

- 1aebec8: The Vite dev server pre-bundles the Unovis `striptags` dependency so pages with charts load in the browser. Development only.

## 1.1.0

### Minor Changes

- 6a3c205: Icons come from `@lucide/vue` (replacing the deprecated `lucide-vue-next`), with `@mts241alikhlash/ui` and `web-shared` 1.1.0.

## 1.0.1

### Patch Changes

- 3a06b99: Update @mts241alikhlash/ui to 1.0.1.

## 1.0.0

### Major Changes

- First stable release.
