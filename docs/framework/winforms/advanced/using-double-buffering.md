---
title: "Verwenden der doppelten Pufferung | Microsoft Docs"
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
  - "Puffern, Doppelte Pufferung"
  - "Doppelte Pufferung"
  - "Flimmern, Vermindern in Windows Forms"
  - "Grafiken, Doppelte Pufferung"
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Verwenden der doppelten Pufferung
Sie können doppelt gepufferte Grafiken verwenden, um das Flimmern in Anwendungen zu reduzieren, die komplexe Zeichenoperationen beinhalten.  .NET Framework enthält integrierte Unterstützung für die doppelte Pufferung. Alternativ können Sie Grafiken manuell verwalten und rendern.  
  
## In diesem Abschnitt  
 [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Enthält eine Einführung in die doppelte Pufferung und erläutert die .NET Framework\-Unterstützung.  
  
 [Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Veranschaulicht, wie die standardmäßige Unterstützung der doppelten Pufferung in .NET Framework eingesetzt wird.  
  
 [Gewusst wie: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Veranschaulicht die Verwaltung der doppelten Pufferung in Anwendungen.  
  
 [Gewusst wie: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Veranschaulicht das Rendern doppelt gepufferter Grafiken.  
  
## Referenz  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Steuerungsmethode zur Aktivierung der doppelten Pufferung.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Stellt Methoden zum Erstellen von Grafikpuffern bereit.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Ermöglicht einer Anwendungsdomäne den Zugriff auf den Kontext gepufferter Grafiken.