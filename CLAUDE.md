# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a multi-project Node.js repository containing various applications built with Express.js, React, Sails.js, Sequelize, and blockchain technologies. The repository serves as a collection of different web applications and APIs with distinct purposes.

## Project Structure & Architecture

### Project Types & Technologies:

1. **Express.js APIs with Sequelize ORM** (challenges, inventories, players, shopping, users):
   - Standard Express app structure with MVC pattern
   - MySQL databases via Sequelize ORM
   - JWT authentication (shopping, users)
   - Passport.js for auth strategies (shopping)
   - File upload capabilities (inventories, shopping)

2. **Sails.js Application** (library_management):
   - Full-featured web application framework
   - Built-in ORM and MVC architecture
   - Asset pipeline with Grunt
   - User authentication system

3. **React Applications** (chat, react-viseo):
   - Create React App setup
   - Material-UI components (react-viseo)

4. **Blockchain/Ethereum DApp** (TMD):
   - Truffle framework for smart contract development
   - Solidity contracts for pet adoption
   - Web3.js integration

### Common Patterns:

- **Database**: Most Express apps use MySQL with Sequelize v5.15.1
- **Views**: Jade/Pug templating for server-rendered apps
- **Authentication**: JWT tokens and Passport.js strategies
- **File Handling**: express-fileupload middleware
- **Validation**: express-validator for input validation

## Common Development Commands

### Express.js Applications (challenges, inventories, players, shopping, users):
```bash
npm start                    # Start production server
npm run devstart            # Start with nodemon (users only)
```

### React Applications (chat, react-viseo):
```bash
npm start                   # Start development server
npm run build              # Build for production
npm test                   # Run tests
```

### Sails.js Application (library_management):
```bash
npm start                  # Start production server
npm test                   # Run linting and tests
npm run lint              # Run ESLint, HTMLHint, and LESSHint
npm run custom-tests      # Run custom test suite
```

### Blockchain Application (TMD):
```bash
npm run dev               # Start lite-server for frontend
```

## Database Configuration

Most projects use Sequelize with MySQL. Database configurations are typically found in:
- `config/config.json` (standard Sequelize config)
- Environment variables for production settings

## Authentication Patterns

- **JWT-based**: Shopping and users apps implement JWT authentication
- **Session-based**: Library management uses Sails.js built-in sessions
- **Passport.js**: Used in shopping app with JWT strategy

## File Structure Conventions

- `routes/` - Express route handlers
- `models/` - Sequelize model definitions
- `views/` - Template files (Jade/Pug/EJS)
- `public/` - Static assets
- `config/` - Configuration files
- `bin/www` - Server startup script (Express apps)

## Testing & Quality

- Sails.js project has comprehensive linting setup
- React apps use Create React App testing framework
- No unified testing strategy across all projects

## Development Notes

- Projects use various Node.js versions and dependency versions
- Some projects may have security vulnerabilities in older dependencies
- Database connections require local MySQL setup
- Blockchain project requires local Ethereum network (Ganache/Testrpc)