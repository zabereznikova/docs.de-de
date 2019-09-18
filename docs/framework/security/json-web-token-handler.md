---
title: JSON-Webtokenhandler
ms.date: 03/30/2017
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
ms.openlocfilehash: 3dc76f3de714fd91d397cc240d02a1a8605fe18b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045332"
---
# <a name="json-web-token-handler"></a>JSON-Webtokenhandler
Die JSON-Webtokenhandler-Erweiterung für Windows Identity Foundation ermöglicht es Ihnen, JSON-Webtoken (JWT) in den Anwendungen zu erstellen und zu überprüfen. Der JWT-Tokenhandler kann so konfiguriert werden, dass er wie andere integrierte Sicherheitstokenhandler in der WIF-Pipeline ausgeführt wird; er kann jedoch auch unabhängig verwendet werden, um die Tokenvalidierung in einfachen Anwendungen auszuführen. Der JWT-Tokenhandler ist besonders nützlich, wenn ein OAuth 2.0-Trägertokenschema verwendet wird, z. B. die Authentifizierung für Microsoft Azure Active Directory.  
  
 Der JWT-Tokenhandler ist als NuGet-Paket verfügbar. Weitere Informationen finden Sie unter [Downloading the JSON Web Token Handler Package (Herunterladen des JSON-Webtokenhandler-Pakets)](downloading-the-json-web-token-handler-package.md).  
  
## <a name="scenarios"></a>Szenarien  
 Der JWT Token Handler ermöglicht die folgenden Hauptszenarien:  
  
- Überprüfen **eines JWT-Tokens in einer Server Anwendung**: In diesem Szenario verfügt ein Unternehmen namens Litware über eine Serveranwendung, die WIF verwendet, um Webanmeldungs Anforderungen zu verarbeiten. Litware möchte, dass die Anwendung in der Lage ist, JWT-Token zur Authentifizierung zu verwenden. Die Anwendung wird mit dem JWT-Tokenhandler aktualisiert, und anschließend wird die Anwendungskonfiguration aktualisiert, um den JWT-Tokenhandler in der WIF-Pipeline hinzuzufügen. Nachdem die Aktualisierungen ausgeführt wurden und eine neue Anfrage in die WIF-Pipeline gelangt, wird das JWT-Token mithilfe des neuen Handlers überprüft und erfolgreich authentifiziert.  
  
- Überprüfen **eines JWT-Tokens in einem Rest-Webdienst**: In diesem Szenario verfügt ein Unternehmen namens Litware über einen Rest-Webdienst, der von Windows Azure Active Directory geschützt wird. Anfragen an den Webdienst müssen von Microsoft Azure AD authentifiziert werden, das nach erfolgreicher Authentifizierung ein JWT-Token ausgibt. Litware hat eine Clientanwendung, die auf den Webdienst zugreifen muss. Der Client stellt eine Anfrage an den Webdienst und präsentiert sein JWT-Token von Microsoft Azure AD, das dann vom Webdienst mithilfe des JWT-Token-Handlers überprüft wird. Nachdem der JWT-Tokenhandler das Token überprüft hat, wird die gewünschte Ressource vom Webdienst an den Client zurückgegeben.  
  
## <a name="features"></a>Features  
 Der JWT-Tokenhandler bietet folgende Funktionen:  
  
- Überprüfen **eines JWT**-Tokens: JWT-Token können durch die Validierungs Logik des tokenhandlers leicht überprüft werden, entweder als Teil der WIF-Pipeline der Anwendung oder unabhängig von WIF.  
  
- **Erstellen Sie ein JWT-Token**: Der JWT-Tokenhandler kann zum Erstellen von JWT-Token zur Autorisierung in downstreamdiensten verwendet werden.
