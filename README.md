# TailwindCss Purging is not working correctly with Docker

## What is working
- TailwindCss is working correctly in development mode
```
npm run dev
```

- Also in production mode with the following command
```
npm run build
npm run start
```

- Also deploying to Vercel WITHOUT docker is working correctly

## What is not working
- Deploying to fly.io with docker (this how fly.io works), is not working correctly. Specifically, the purging of tailwindcss is not working correctly. You can see by inspecting the css files included that the `@tailwind` commands are not being replaced with used classes.

- To insure that the problem is because of docker, I've build and run the project with docker locally and it indeed has the same problem. You can do the same by running the following commands:
```
docker build -t remix-tailwind-test .
docker run -e PORT=8080 -p 8080:8080 remix-tailwind-test
```

