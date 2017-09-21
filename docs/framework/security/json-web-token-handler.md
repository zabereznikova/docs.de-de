---
title: JSON-Webtokenhandler
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
caps.latest.revision: 5
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6772d484fa4d0ed3948ecee26adb2cf886340f11
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="json-web-token-handler"></a>JSON-Webtokenhandler
Die JSON-Webtokenhandler-Erweiterung für Windows Identity Foundation ermöglicht es Ihnen, JSON-Webtoken (JWT) in den Anwendungen zu erstellen und zu überprüfen. Der JWT-Tokenhandler kann so konfiguriert werden, dass er wie andere integrierte Sicherheitstokenhandler in der WIF-Pipeline ausgeführt wird; er kann jedoch auch unabhängig verwendet werden, um die Tokenüberprüfung in einfachen Anwendungen auszuführen. Der JWT-Tokenhandler ist besonders nützlich, wenn ein OAuth 2.0-Trägertokenschema verwendet wird, z. B. die Authentifizierung für Microsoft Azure Active Directory.  
  
 Der JWT-Tokenhandler ist als NuGet-Paket verfügbar. Weitere Informationen finden Sie unter [Downloading the JSON Web Token Handler Package (Herunterladen des JSON-Webtokenhandler-Pakets)](../../../docs/framework/security/downloading-the-json-web-token-handler-package.md).  
  
## <a name="scenarios"></a>Szenarien  
 Der JWT Token Handler ermöglicht die folgenden Hauptszenarien:  
  
-   **Überprüfen eines JWT-Tokens in einer Serveranwendung**: In diesem Szenario verfügt ein Unternehmen namens Litware über eine Serveranwendung, die Webanmeldungsanfragen mit WIF bearbeitet. Litware möchte, dass die Anwendung in der Lage ist, JWT-Token zur Authentifizierung zu verwenden. Die Anwendung wird mit dem JWT-Tokenhandler aktualisiert, und anschließend wird die Anwendungskonfiguration aktualisiert, um den JWT-Tokenhandler in der WIF-Pipeline hinzuzufügen. Nachdem die Aktualisierungen ausgeführt wurden und eine neue Anfrage in die WIF-Pipeline gelangt, wird das JWT-Token mithilfe des neuen Handlers überprüft und erfolgreich authentifiziert.  
  
-   **Überprüfen eines JWT-Tokens in einem REST-Webdienst**: In diesem Szenario verfügt ein Unternehmen namens Litware über einen REST-Webdienst, der durch Microsoft Azure Active Directory gesichert ist. Anfragen an den Webdienst müssen von Microsoft Azure AD authentifiziert werden, das nach erfolgreicher Authentifizierung ein JWT-Token ausgibt. Litware hat eine Clientanwendung, die auf den Webdienst zugreifen muss. Der Client stellt eine Anfrage an den Webdienst und präsentiert sein JWT-Token von Microsoft Azure AD, das dann vom Webdienst mithilfe des JWT-Token-Handlers überprüft wird. Nachdem der JWT-Tokenhandler das Token überprüft hat, wird die gewünschte Ressource vom Webdienst an den Client zurückgegeben.  
  
## <a name="features"></a>Features  
 Der JWT-Tokenhandler bietet folgende Funktionen:  
  
-   **Überprüfen eines JWT-Tokens**: JWT-Token können durch die Tokenvalidierungslogik des Handlers leicht überprüft werden, entweder im Rahmen der WIF-Pipeline der Anwendung oder durch einen Aufruf unabhängig von WIF.  
  
-   **Erstellen eines JWT-Tokens**: Mit dem JWT-Tokenhandler können JWT-Token zur Autorisierung in Downstreamdiensten erstellt werden.

