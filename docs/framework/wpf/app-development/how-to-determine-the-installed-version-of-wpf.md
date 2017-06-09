---
title: "Gewusst wie: Bestimmen der installierten WPF-Version | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Version, Suchen"
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Gewusst wie: Bestimmen der installierten WPF-Version
Die Versionsnummer für die momentan installierte Version von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] befindet sich in der **Registrierung**.  
  
 So suchen Sie die Versionsnummer:  
  
1.  Klicken Sie im **Startmenü** auf **Ausführen**.  
  
2.  Geben Sie unter **Öffnen** den Befehl **regedit.exe** ein.  
  
3.  Öffnen Sie den folgenden Schlüssel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Die Versionsnummer von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist unter dem Wert **Version** gespeichert.