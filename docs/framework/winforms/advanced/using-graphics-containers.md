---
title: "Verwenden von Grafikcontainern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], Grafikcontainer"
  - "Grafikcontainer"
  - "Grafiken, Verwenden von Containern"
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Verwenden von Grafikcontainern
Ein <xref:System.Drawing.Graphics>\-Objekt stellt Methoden zur Anzeige von Vektorbildern, Rasterbildern und Text bereit, z. B. <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A> und <xref:System.Drawing.Graphics.DrawString%2A>.  Darüber hinaus verfügt ein <xref:System.Drawing.Graphics>\-Objekt über verschiedene Eigenschaften, die die Qualität und Ausrichtung der gezeichneten Elemente beeinflussen.  Durch die **SmoothingMode**\-Eigenschaft wird z. B. festgelegt, ob Antialiasing auf Linien und Kurven angewendet wird, und die globale Transformationseigenschaft beinflusst die Position und den Drehwinkel der gezeichneten Elemente.  
  
 Ein <xref:System.Drawing.Graphics>\-Objekt ist einem bestimmten Anzeigegerät zugeordnet.  Wird ein <xref:System.Drawing.Graphics>\-Objekt zum Zeichnen innerhalb eines Fensters verwendet, ist das <xref:System.Drawing.Graphics>\-Objekt zusätzlich mit dem jeweiligen Fenster verknüpft.  
  
 Konzeptionell kann ein <xref:System.Drawing.Graphics>\-Objekt mit einem Container verglichen werden, da es eine Reihe von Eigenschaften enthält, die das Zeichnen beeinflussen, und mit gerätespezifischen Informationen verknüpft ist.  Sie können einen sekundären Container in einem vorhandenen <xref:System.Drawing.Graphics>\-Objekt erstellen, indem Sie die <xref:System.Drawing.Graphics.BeginContainer%2A>\-Methode dieses <xref:System.Drawing.Graphics>\-Objekts aufrufen.  
  
## In diesem Abschnitt  
 [Verwalten des Zustands eines Graphics\-Objekts](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Beschreibt, wie die Qualitätseinstellungen, der Clippingbereich und Transformationen eines <xref:System.Drawing.Graphics>\-Objekts verwaltet werden.  
  
 [Verwenden geschachtelter Grafikcontainer](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Zeigt, wie Container verwendet werden, um den Zustand des <xref:System.Drawing.Graphics>\-Objekts zu steuern.