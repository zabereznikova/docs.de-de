---
title: "Deploying Applications That Reference Power Packs Controls (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Power Packs, deploying"
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Deploying Applications That Reference Power Packs Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie eine Anwendung bereitstellen, die auf Power Packs\-Steuerelemente verweist \(<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\), müssen die Steuerelemente auf dem Zielcomputer installiert werden.  
  
## Installieren der Power Packs\-Steuerelemente als Voraussetzung  
 Zur erfolgreichen Bereitstellung einer Anwendung müssen Sie auch alle Komponenten bereitstellen, auf die von der Anwendung verwiesen wird.  Das Installieren erforderlicher Komponenten wird auch als *Bootstrapping* bezeichnet.  
  
 Beim Installieren von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] auf dem Entwicklungscomputer wird dem [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]\-Bootstrapper\-Verzeichnis ein Power Packs\-Bootstrapperpaket hinzugefügt.  Dieses Paket ist dann verfügbar, wenn Sie den Anleitungen zum Hinzufügen erforderlicher Komponenten für die [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)]\- oder Windows Installer\-Bereitstellung folgen.  
  
 Standardmäßig werden Bootstrapperkomponenten vom gleichen Speicherort wie das Installationspaket bereitgestellt.  Wahlweise können Sie die Komponenten auch über eine URL oder einen Dateifreigabespeicherort bereitstellen, von dem die Benutzer sie nach Bedarf herunterladen können.  
  
> [!NOTE]
>  Zum Installieren von Bootstrapperkomponenten muss der Benutzer möglicherweise Administrator\- oder ähnliche Benutzerberechtigungen auf dem Computer besitzen.  Bei [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)]\-Anwendungen bedeutet dies, dass der Benutzer unabhängig von der für die Anwendung angegebenen Sicherheitsebene zum Installieren der Anwendung Administratorberechtigungen benötigt.  Nach der Installation kann der Benutzer die Anwendung ohne Administratorberechtigungen ausführen.  
  
 Bei der Installation wird der Benutzer zum Installieren der Power Packs\-Steuerelemente aufgefordert, wenn diese auf dem Zielcomputer noch nicht vorhanden sind.  
  
 Alternativ zum Bootstrapping können die Power Packs\-Steuerelemente mit einem elektronischen Softwareverteilungssystem wie Microsoft Systems Management Server \(SMS\) vorab bereitgestellt werden.  
  
## Siehe auch  
 [How to: Install Prerequisites in Windows Installer Deployment](http://msdn.microsoft.com/de-de/653fc868-2486-429c-b75e-2f9d0c7f6619)   
 [How to: Install Prerequisites with a ClickOnce Application](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Not in Build: Choosing a Deployment Strategy](http://msdn.microsoft.com/de-de/ecd632d8-063c-4028-b785-81bba045107b)   
 [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)