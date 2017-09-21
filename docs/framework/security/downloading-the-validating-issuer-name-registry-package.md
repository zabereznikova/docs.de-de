---
title: Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: 3
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d7aa4e4010da70f90bb18db9cd4e8179925bb58d
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="downloading-the-validating-issuer-name-registry-package"></a>Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
In diesem Thema wird erläutert, wie "Überprüfen der Ausstellernamensregistrierung" (VINR) im Projekt heruntergeladen und verwendet wird.  
  
## <a name="downloading-the-validating-issuer-name-registry"></a>Herunterladen von "Überprüfen der Ausstellernamensregistrierung" (VINR)  
 Die VINR ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt. Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](http://nuget.org), um es zu installieren. Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie deren Seite auf NuGet aufrufen: [Überprüfen der Ausstellernamensregistrierung auf NuGet von Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/).  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a>Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe des Paket-Managers GUI  
  
1.  Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.  
  
2.  Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `ValidatingIssuerNameRegistry` ein, und drücken Sie die **EINGABETASTE**.  
  
3.  Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.  
  
4.  Das Paket wird heruntergeladen. Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz. Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.  
  
5.  Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a>Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe der Paket-Manager-Konsole  
  
1.  Klicken Sie in Visual Studio auf **Extras**, den **Bibliotheks-Paket-Manager** und anschließend auf **Paket-Manager-Konsole**.  
  
2.  Die **Paket-Manager-Konsole** wird angezeigt. Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.

