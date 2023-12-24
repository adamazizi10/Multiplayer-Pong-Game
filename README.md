<h1 align="center">MultiPong</h1>

  <p align="center" >
    <i>A realtime online multiplayer pong game.</i>
    <br>
  </p>

## Installation and Running Dev Server

1. Clone the repo or download the zip
2. Make sure you have the correct node and python versions installed, we've tested the minimum versions below:
   - Node: v17.4.0
   - Python: v3.12.0
3. Install dependencies
   - Frontend
     1. Navigate to the frontend directory and run `npm install`
   - Backend
     - Navigate to the backend directory and run `pip install -r requirements.txt`
       - If you're running it on windows use `pip install -r requirementsWindows.txt`
4. Run the app
   - Frontend
     - Navigate to the frontend directory and run `npm run start-react`
   - Game
     - Open the code in VS Code after downloading the Five Server Extension https://marketplace.visualstudio.com/items?itemName=yandeu.five-server
     - Right click `frontend/index.html` from the file tree, and click "Open with Five Server"
     - The frontend urls can be configured from the `.env.development` file.
   - Backend
     - Navigate to the `backend/pong_backend` directory and run `python manage.py runserver`
## Snapshots
# Landing Page
<img width="1512" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/10f26e6f-d71f-44ad-899d-d96125628ca8">

# Login Page
<img width="1512" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/217b53f2-9689-4a36-a8eb-b9c300a582d9">

# Sign Up Page
<img width="1512" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/dfeb6653-50c0-4ebd-a353-b11ac0a69a76">

# Play Tab
<img width="1512" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/cf1f2909-c30e-44da-82b8-88e7d55c1470">




# Match History Tab
<img width="1494" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/bcea2962-12a0-4b52-95ed-13c01f44d411">

# Leaderboard Tab
<img width="1493" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/1547ce0e-e78e-40e2-b338-edf8f2021c71">

# Profile Tab
<img width="1496" alt="image" src="https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/aa9dc18e-fdf6-4262-9102-8010408bc6a7">

# Game Lobby
![image](https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/8e0c5ca3-e807-47a6-82ca-031b3de19820)

# Example of 8 Players playing at once. The green represents the player, red represents all the oponents
![image](https://github.com/adamazizi10/Multiplayer-Pong-Game/assets/106051947/1a7a9c49-45e9-462d-8405-a9176ecb1aeb)




# Additional Info
## Usage

- Navigate to http://localhost:3000/ in your browser for the game
- Navigate to http://localhost:8000/swagger/ in your browser for the API documentation
  - More in-depth documentation can be found in the `backend/README.md` file
- Navigate to http://localhost:8000/admin/ in your browser for the admin panel
  - Username: `test`
  - Password: `test`

## Deploying to Production

### Frontend

1. CD into the frontend directory
2. Run `npm build` to build the production build
   1. The URL can be configured via the `.env.production` file
3. Install serve to deploy the frontend
   1. `npm install -g serve`
4. Serve the frontend via `serve -s build`

### Game

1. Open the code in VS Code after downloading the Five Server Extension https://marketplace.visualstudio.com/items?itemName=yandeu.five-server
2. Right click `frontend/index.html` from the file tree, and click "Open with Five Server"

### Backend

1. Navigate to `backend/pong_backend` (not `backend/pong_backend/pong_backend`)
2. Run `python manage.py runserver`
   1. Run `python manage.py runserver 0.0.0.0:8000` if you want to serve it on LAN

## Troubleshooting

- It's recommended to use a virtual enviroment such as venv or conda for the backend
  - https://code.visualstudio.com/docs/python/environments#:~:text=Using%20the%20Create%20Environment%20command,environment%20types%3A%20Venv%20or%20Conda.
- If the frontend has any issues with module, run `npm ci` in the frontend directory to cleanly reinstall everything
- Occasionally Django will thrrow a migration error:
  1. CD into `backend/pong_backend`
  2. Run `python manage.py makemigrations`
  3. Run `python manage.py migrate`
  4. Run the django server
- If match history doesn't seem to be saving, make sure that local clients are on different browser sessions, and one logged in user isn't in the same game twice
  - This is due to the way our backend is designed, where players must be unique or a guest in each match
- If the game start is freezing or the paddles aren't loading, make sure all browsers are viewable and focused if possible
  - This is because browsers attempt to freeze javascript if the browser is in the background to save resources

# End of User Guide
