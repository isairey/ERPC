# ⚡ eRPC Framework

<p align="center">
  <b>Framework RPC eficiente, extensible y de alto rendimiento en Go</b>
</p>

---

## 📌 Descripción

**eRPC** es un framework RPC diseñado para ofrecer alto rendimiento, flexibilidad y facilidad de uso en aplicaciones modernas.

Es ideal para:

* Microservicios
* Sistemas distribuidos
* Aplicaciones en tiempo real (chat, gaming, IM)
* Arquitecturas Peer-to-Peer

---

## 🚀 Instalación

### Requisitos

* Go ≥ 1.18

### Instalación

```bash
GO111MODULE=on go get -u github.com/andeya/erpc/v7
```

### Importación

```go
import "github.com/andeya/erpc/v7"
```

---

## ✨ Características principales

* 🔁 API unificada para cliente y servidor
* 🧩 Arquitectura modular (peer, router, session, plugin, etc.)
* 🌐 Compatible con múltiples protocolos:

  * JSON
  * Protobuf
  * Thrift
  * XML
* ⚡ Alto rendimiento con sockets no bloqueantes
* 🔌 Sistema de plugins extensible
* 🔐 Soporte para seguridad y autenticación
* 📡 Soporte para múltiples redes:

  * TCP / TCP4 / TCP6
  * UNIX
  * WebSocket
  * QUIC / KCP

---

## 🧠 Arquitectura

El framework está basado en componentes clave:

* **Peer** → Nodo principal (cliente/servidor)
* **Session** → Manejo de conexiones
* **Router** → Gestión de rutas RPC
* **Codec** → Serialización de datos
* **Plugin** → Extensión de funcionalidades

---

## ⚙️ Ejemplo básico

### 🖥️ Servidor

```go
srv := erpc.NewPeer(erpc.PeerConfig{
  ListenPort: 9090,
})

srv.RouteCall(new(Math))
srv.ListenAndServe()
```

---

### 💻 Cliente

```go
cli := erpc.NewPeer(erpc.PeerConfig{})

sess, _ := cli.Dial(":9090")

var result int
sess.Call("/math/add", []int{1,2,3}, &result)
```

---

## 📊 Rendimiento

eRPC está optimizado para alto rendimiento:

* Baja latencia
* Alto throughput (TPS)
* Manejo eficiente de concurrencia

Ideal para sistemas que requieren **alto volumen de transacciones**.

---

## 🔌 Extensiones

### Codecs disponibles

* JSON
* Protobuf
* Thrift
* XML
* Plain / Form

---

### Plugins incluidos

* 🔐 Autenticación
* ❤️ Heartbeat
* 🔄 Proxy
* 🛡️ Seguridad
* ⚙️ Control de sobrecarga

---

### Protocolos soportados

* rawproto (alto rendimiento)
* jsonproto
* pbproto
* thriftproto
* httproto

---

## 🧪 Casos de uso

Proyectos construidos con eRPC:

* Sistemas de microservicios
* Crawlers distribuidos
* Plataformas en tiempo real

---

## ⚙️ Configuración

Ejemplo de configuración básica:

```go
erpc.PeerConfig{
  Network: "tcp",
  ListenPort: 9090,
  PrintDetail: true,
}
```

---

## 📈 Optimización

* Configuración de buffers de socket
* Control de tamaño de mensajes
* KeepAlive y reconexión automática

---

## 📄 Licencia

Este proyecto está bajo la licencia **Apache 2.0**.

---

## ⭐ Soporte

Si este proyecto te resulta útil:

👉 Dale una estrella ⭐ en GitHub
👉 Contribuye al desarrollo 🚀

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas.
Consulta el archivo `CONTRIBUTING.md` para más información.

---

