---
title: "Herunterladen des Pakets zur Validierung der Ausstellernamenregistration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
In diesem Thema wird erläutert, wie "Überprüfen der Ausstellernamensregistrierung" \(VINR\) im Projekt heruntergeladen und verwendet wird.  
  
## Herunterladen von "Überprüfen der Ausstellernamensregistrierung" \(VINR\)  
 Die VINR ist als NuGet\-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt.  Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](http://nuget.org), um es zu installieren.  Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie deren Seite auf NuGet aufrufen: [Überprüfen der Ausstellernamensregistrierung auf NuGet von Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)  
  
#### Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe des Paket\-Managers GUI  
  
1.  Klicken Sie in Visual Studio im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **NuGet\-Pakete verwalten**.  
  
2.  Klicken Sie im Fenster **NuGet\-Pakete verwalten** auf das Suchfeld, geben Sie `ValidatingIssuerNameRegistry` ein, und drücken Sie die **EINGABETASTE**.  
  
3.  Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.  
  
4.  Das Paket wird heruntergeladen.  Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz.  Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **I Accept**.  
  
5.  Die neuesten VINR\-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.  
  
#### Herunterladen von "Überprüfen der Ausstellernamensregistrierung" mithilfe der Paket\-Manager\-Konsole  
  
1.  Klicken Sie in Visual Studio auf **Extras**, **Bibliothek\-Paket\-Manager** und dann auf **Paket\-Manager\-Konsole**.  
  
2.  Die **Paket\-Manager\-Konsole** wird angezeigt.  Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  Die neuesten VINR\-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.