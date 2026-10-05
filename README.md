Clone the repo 

docker build -t dbimage database/ <br />
docker build -t authimage auth/ <br />
docker build -t bookimage book/ <br />
docker build -t borrowimage borrow/ <br />
docker build -t appimage . <br /> <br /> <br /> <br />


docker network create mynet <br /> <br /> <br /> <br />


docker run -d --name db -p 3306:3306 --network mynet dbimage <br />
docker run -d --name auth_service --network mynet  -p 5001:5001 authimage <br />
docker run -d --name book_service -p 5002:5002 --network mynet bookimage <br />
docker run -d --name borrow_service  -p 5003:5003 --network mynet borrowimage <br />
docker run -d --name frontend  -p 5000:5000 --network mynet  appimage <br /> 

 <img width="1402" height="1000" alt="image" src="https://github.com/user-attachments/assets/c185936d-35ac-4422-b2ca-9443f19f475e" />

The Final Application Access:
<img width="1735" height="966" alt="Screenshot 2026-10-05 182747" src="https://github.com/user-attachments/assets/76a2d8d2-2e46-4b4a-b058-19c0eabd37c8" />
