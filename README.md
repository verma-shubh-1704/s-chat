# chat-app
#### A interactive Chat Application

> This is a Node.js application following the instuctions of [Udemy Course](https://www.udemy.com/course/the-complete-nodejs-developer-course-2/).

The libraries used in this project are:
```
- express
- socket.io
```

#### brief Details of project

###### importing standard libraries
```
const express = require('express')
const http = require('http')
const path = require('path')
const socketio = require('socket.io')
```

###### create express APP, server and IO
```
const app = express()
const server = http.createServer(app)
const io = socketio(server)
```

###### handle client connections
```
io.on('connection', (socket) => {
...
...
...
})
```

###### sending message to client
> socket.emit('message', getMessage('Admin', 'Welcome!'))

###### client socket connection joining a room
> socket.join(message.room)

###### boradcasting a message to all users in room except the current client
> socket.broadcast.to(message.room).emit('message', getMessage('Admin', `${message.username} has joined!`))

###### boradcasting a message to all users in room
> io.to(message.room).emit('roomData', { room: message.room, users: usersInRooms })

