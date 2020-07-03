---
title: Web- und Socketberechtigungen
description: Informationen dazu, wie die Klassen „WebPermission“ und „SocketPermission“ Internetsicherheit für die Verwendung des System.Net-Namespace im .NET Framework bereitstellen
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: 08ae360e8097f7281631da2a3f9846994dfbf5b6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501897"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="b1684-103">Web- und Socketberechtigungen</span><span class="sxs-lookup"><span data-stu-id="b1684-103">Web and Socket Permissions</span></span>
<span data-ttu-id="b1684-104">Internetsicherheit für Anwendungen, die den <xref:System.Net>-Namespace verwenden, wird von den <xref:System.Net.WebPermission>- und <xref:System.Net.SocketPermission>-Klassen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b1684-104">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="b1684-105">Die **WebPermission**-Klasse steuert das Recht einer Anwendung, Daten aus einem URI abzufragen, oder einen URI für das Internet zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b1684-105">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="b1684-106">Die **SocketPermission**-Klasse steuert das Recht einer Anwendung zur Verwendung von <xref:System.Net.Sockets.Socket> für das Annehmen von Daten auf einem lokalen Port oder für das Kontaktieren von Remotegeräten, die ein Transportprotokoll an einer anderen Adresse verwenden, und die auf dem Host, der Portnummer und dem Transportprotokoll des Sockets basieren.</span><span class="sxs-lookup"><span data-stu-id="b1684-106">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="b1684-107">Welche Berechtigungsklasse Sie verwenden, hängt von Ihrem Anwendungstyp ab.</span><span class="sxs-lookup"><span data-stu-id="b1684-107">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="b1684-108">Anwendungen, die <xref:System.Net.WebRequest> und seine Nachfolger verwenden, sollten die **WebPermission**-Klasse verwenden, um Berechtigungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b1684-108">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="b1684-109">Anwendungen, die Zugriff auf Socketebene verwenden, sollten die **SocketPermission**-Klasse verwenden, um Berechtigungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b1684-109">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="b1684-110">**WebPermission** und **SocketPermission** definieren zwei Berechtigungen: Akzeptieren und Verbinden.</span><span class="sxs-lookup"><span data-stu-id="b1684-110">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="b1684-111">„Akzeptieren“ gewährt der Anwendung das Recht, eine eingehende Verbindung von einer anderen Partei zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="b1684-111">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="b1684-112">„Verbinden“ gewährt der Anwendung das Recht, eine eingehende Verbindung von einer anderen Partei zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="b1684-112">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="b1684-113">Für **SocketPermission**-Instanzen bedeutet „Akzeptieren“, dass eine Anwendung eingehende Verbindungen auf einer lokalen Transportadresse annehmen kann. „Verbinden“ bedeutet, dass eine Anwendung eine Verbindung zu einer Remotetransportadresse (oder einer lokalen Transportadresse) herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="b1684-113">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="b1684-114">Für **WebPermission**-Instanzen bedeutet „Akzeptieren“, dass eine Anwendung den von **WebPermission** gesteuerten URI weltweit exportieren kann. „Verbinden“ bedeutet, dass eine Anwendung Zugriff auf diesen URI hat (egal ob Remote oder lokal).</span><span class="sxs-lookup"><span data-stu-id="b1684-114">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1684-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1684-115">See also</span></span>

- [<span data-ttu-id="b1684-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b1684-116">Security</span></span>](../../standard/security/index.md)
- [<span data-ttu-id="b1684-117">Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)</span><span class="sxs-lookup"><span data-stu-id="b1684-117">Security in Network Programming</span></span>](security-in-network-programming.md)
