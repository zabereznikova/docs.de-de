---
title: JSON-Webtokenhandler
ms.date: 03/30/2017
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
ms.openlocfilehash: 5ffaaaebd87c63b784a749f8998d43d14fe768e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641108"
---
# <a name="json-web-token-handler"></a>JSON-Webtokenhandler
Die JSON-Webtokenhandler-Erweiterung für Windows Identity Foundation ermöglicht es Ihnen, JSON-Webtoken (JWT) in den Anwendungen zu erstellen und zu überprüfen. Der JWT-Tokenhandler kann so konfiguriert werden, dass er wie andere integrierte Sicherheitstokenhandler in der WIF-Pipeline ausgeführt wird; er kann jedoch auch unabhängig verwendet werden, um die Tokenvalidierung in einfachen Anwendungen auszuführen. Der JWT-Tokenhandler ist besonders nützlich, wenn ein OAuth 2.0-Trägertokenschema verwendet wird, z. B. die Authentifizierung für Microsoft Azure Active Directory.  
  
 Der JWT-Tokenhandler ist als NuGet-Paket verfügbar. Weitere Informationen finden Sie unter [Downloading the JSON Web Token Handler Package (Herunterladen des JSON-Webtokenhandler-Pakets)](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md).  
  
## <a name="scenarios"></a>Szenarien  
 Der JWT Token Handler ermöglicht die folgenden Hauptszenarien:  
  
- **Überprüfen Sie ein JWT-Token in einer Serveranwendung**: In diesem Szenario verfügt ein Unternehmen namens Litware eine Serveranwendung, die WIF verwendet wird, zum Verarbeiten von webanforderungen anmelden. Litware möchte, dass die Anwendung in der Lage ist, JWT-Token zur Authentifizierung zu verwenden. Die Anwendung wird mit dem JWT-Tokenhandler aktualisiert, und anschließend wird die Anwendungskonfiguration aktualisiert, um den JWT-Tokenhandler in der WIF-Pipeline hinzuzufügen. Nachdem die Aktualisierungen ausgeführt wurden und eine neue Anfrage in die WIF-Pipeline gelangt, wird das JWT-Token mithilfe des neuen Handlers überprüft und erfolgreich authentifiziert.  
  
- **Überprüfen ein JWT-Tokens in einem REST-Webdienst**: In diesem Szenario hat ein Unternehmen namens Litware über eine REST-Webdienst, der von Windows Azure Active Directory gesichert wird. Anfragen an den Webdienst müssen von Microsoft Azure AD authentifiziert werden, das nach erfolgreicher Authentifizierung ein JWT-Token ausgibt. Litware hat eine Clientanwendung, die auf den Webdienst zugreifen muss. Der Client stellt eine Anfrage an den Webdienst und präsentiert sein JWT-Token von Microsoft Azure AD, das dann vom Webdienst mithilfe des JWT-Token-Handlers überprüft wird. Nachdem der JWT-Tokenhandler das Token überprüft hat, wird die gewünschte Ressource vom Webdienst an den Client zurückgegeben.  
  
## <a name="features"></a>Features  
 Der JWT-Tokenhandler bietet folgende Funktionen:  
  
- **Überprüfen eines JWT-Tokens**: JWT-Token können einfach durch die tokenvalidierungslogik des Handlers Validierungslogik, entweder im Rahmen der WIF-Pipeline der Anwendung überprüft oder Aufruf unabhängig von WIF  
  
- **Erstellen Sie ein JWT Token**: Der JWT-Tokenhandler kann verwendet werden, um das JWT-Token zur Autorisierung in downstreamdiensten erstellt
