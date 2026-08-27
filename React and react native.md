npm create vite@latest my-react-app -- --template react
npm create vite@latest setting-up-typescript -- --template react-ts

Node -runtime
npm -package manager

-------------------------------
typescript:
mkdir ~/typescript-test
cd ~/typescript-test

npm init -y
npm install --save-dev typescript
npx tsc --init

npx tsc hello.ts --ignoreConfig
node hello.js

run directly:
npm install --save-dev tsx
npx tsx hello.ts

### A useful workflow:
Check types:
npx tsc --noEmit

Execute:
npx tsx hello.ts



npx kill-port 5173

## Next.js
npx create-next-app@latest


## Tests
npm install -D vitest