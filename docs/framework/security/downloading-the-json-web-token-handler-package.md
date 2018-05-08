---
title: Herunterladen des JSON-Webtokenhandler-Pakets
ms.date: 03/30/2017
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 5a4846a5ec92324105f41b320d0d77f8749c28f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="downloading-the-json-web-token-handler-package"></a>Herunterladen des JSON-Webtokenhandler-Pakets
In diesem Thema wird erläutert, wie der JSON-Webtokenhandler im Projekt heruntergeladen und verwendet wird.  
  
## <a name="downloading-the-json-web-token-handler"></a>Herunterladen des JSON-Webtokenhandlers  
 Die JSON-Webtokenhandler-Erweiterung ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt. Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](http://nuget.org), um es zu installieren. Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie auf NuGet [die Seite für den JSON-Webtokenhandler](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/) aufrufen.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a>Herunterladen des JSON-Webtokenhandlers mithilfe der Paket-Manager-GUI  
  
1.  Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.  
  
2.  Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `JWT Token Handler` ein, und drücken Sie die **EINGABETASTE**.  
  
3.  Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.  
  
4.  Das Paket wird heruntergeladen. Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz. Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.  
  
5.  Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a>Herunterladen des JSON-Webtokenhandlers mithilfe der Paket-Manager-Konsole  
  
1.  Klicken Sie in Visual Studio auf **Extras**, den **Bibliotheks-Paket-Manager** und anschließend auf **Paket-Manager-Konsole**.  
  
2.  Die **Paket-Manager-Konsole** wird angezeigt. Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.
