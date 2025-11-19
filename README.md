# Chess101 (016 Chess)

A simple web-based chess prototype using Node.js, Express, EJS and Socket.IO with game logic provided by `chess.js`.

**What this project is**: a small, educational implementation showing a realtime chess UI backed by server-side logic and sockets.

**Highlights**
- **Realtime multiplayer**: uses `socket.io` to broadcast moves and sync game state.
- **Rule enforcement**: `chess.js` validates moves and maintains game state.
- **Server-rendered UI**: page templates in `views/` with client JS in `public/js`.

**Quick Start (Windows PowerShell)**
- **Clone / open project**: `cd "c:\Users\prana\Desktop\Pranav - 2\W\Projects\016 Chess"`
- **Install deps**:
```powershell
npm install
```
- **Start server** (production-style):
```powershell
npm start
```
- **Run in development** (optional): install `nodemon` and run the dev script:
```powershell
npm install -D nodemon
npm run dev
```

Open your browser at `http://localhost:3000` (or the port configured in `app.js` / `PORT` env var).

**Available npm scripts**
- `npm start` — runs `node app.js` to start the server.
- `npm run dev` — runs `nodemon app.js` (requires installing `nodemon` as a dev dependency).

**Project Structure**
- `app.js`: Express server, Socket.IO setup and routing.
- `package.json`: dependency list and npm scripts.
- `views/` — EJS templates (main page: `views/index.ejs`).
- `public/` — static assets served to the browser.
  - `public/js/chessGame.js` — client-side UI and socket handling.
  - `public/css/` — styles.

**How it works (brief)**
- Server serves the initial HTML via EJS and establishes Socket.IO connections.
- Clients emit move events; server validates moves (using `chess.js`) and broadcasts updates.
- Client updates the board UI and move history from socket messages.

**Development tips**
- Use `console.log` or a debugger in `app.js` and `public/js/chessGame.js` to trace socket events.
- Add unit tests around move validation by calling `chess.js` directly.