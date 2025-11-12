# Fresh Demo

A Deno full-stack Web application demo project based on the [Fresh](https://fresh.deno.dev/) framework. Fresh is a modern Web framework designed for Deno, supporting Islands architecture and zero configuration.

## Tech Stack

- **Deno**: Latest version
- **Fresh**: 2.1.3+
- **Preact**: 10.27.2
- **Vite**: 7.1.3
- **Tailwind CSS**: 4.1.10
- **DaisyUI**: 5.3.9

## Project Structure

```
fresh-demo/
├── routes/              # File-system-based routing
│   └── ...
├── islands/             # Interactive Islands components
│   └── ...
├── components/          # Shared components
│   └── ...
├── static/              # Static assets
├── main.ts              # Application entry point and configuration
├── deno.json            # Deno configuration
├── vite.config.ts       # Vite configuration
└── README.md
```

## Features

- Islands architecture (partial hydration)
- File-system-based routing
- Server-Side Rendering (SSR)
- Zero-configuration setup
- TypeScript support
- Tailwind CSS integration
- Hot reload development experience

## Quick Start

### Prerequisites

- [Deno](https://deno.com/) latest version

### Installation and Running

```bash
# Run development server
deno task dev
# Or
deno task start
```

The application will start at `http://localhost:8000`.

### Build and Deploy

```bash
# Build production version
deno task build

# Start production server
deno task start

# Code check
deno task check
```

## Project Features

### Islands Architecture

Fresh uses Islands architecture:
- Server-side rendering by default
- Only interactive components are hydrated on the client
- Smaller JavaScript bundles
- Faster initial loading

### Routing System

File-system-based routing:
- `routes/` directory defines routes
- Automatically handles dynamic routes
- Middleware support
- API routes support

### Example Routes

- **`/api/:name`**: API route example
- **`/api2/:name`**: Programmatically defined route

## Development

### Hot Reload

Fresh provides fast refresh functionality that automatically updates when code is modified.

### Middleware

Supports middleware system:

```typescript
app.use(async (ctx) => {
  ctx.state.shared = "hello";
  return await ctx.next();
});
```

### Static Files

Static file serving:

```typescript
app.use(staticFiles());
```

## Code Description

### Main Application (`main.ts`)

Application configuration includes:
- Static file serving
- Middleware definitions
- Route registration
- File-system routing integration

### Islands

Interactive components placed in `islands/` directory:
- Only run on the client
- Automatic hydration
- Support for Preact Hooks

### Components

Shared components placed in `components/` directory:
- Can be used on both server and client
- Support for JSX/TSX

## Deployment

### Deno Deploy (Recommended)

Fresh applications can be deployed to Deno Deploy with one click:

```bash
# Using Deno Deploy CLI
deployctl deploy --project=your-project
```

### Other Platforms

- Docker
- Self-hosted servers
- Any platform supporting Deno

## Advantages

### Performance

- Zero JavaScript by default (Islands architecture)
- Fast server-side rendering
- Optimized resource loading

### Development Experience

- Zero configuration
- Native TypeScript support
- Fast feedback loop
- Modern toolchain

## References

- [Fresh Official Website](https://fresh.deno.dev/)
- [Fresh Documentation](https://fresh.deno.dev/docs)
- [Deno Documentation](https://deno.com/manual)
- [Preact Documentation](https://preactjs.com/)
