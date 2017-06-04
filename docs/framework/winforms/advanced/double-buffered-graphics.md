---
title: "Doppelt gepufferte Grafiken | Microsoft Docs"
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
  - "Doppelte Pufferung"
  - "Beispiele [Windows Forms], Doppelt gepufferte Grafiken"
  - "Flimmern, Reduzieren mit doppelter Pufferung"
  - "Grafiken, Doppelt gepuffert"
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Doppelt gepufferte Grafiken
Flimmern ist ein häufiges Problem beim Programmieren von Grafiken.  Grafikoperationen, die mehrere komplexe Zeichenvorgänge erfordern, können dazu führen, dass gerenderte Bilder flimmern oder anderweitig nicht korrekt dargestellt werden.  Um diese Probleme zu beheben, stellt .NET Framework Zugriff auf doppelte Pufferung bereit.  
  
 Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben.  Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert.  Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert.  Da auf dem Bildschirm nur eine Grafikoperation ausgeführt wird, wird das durch komplexe Zeichenoperationen ausgelöste Bildflimmern beseitigt.  
  
## Standardmäßige doppelte Pufferung  
 Die einfachste Möglichkeit, die doppelte Pufferung in Anwendungen zu verwenden, bietet die doppelte Pufferung für Formulare und Steuerelemente, die standardmäßig von .NET Framework bereitgestellt wird.  Sie können die standardmäßige doppelte Pufferung für Windows Forms und erstellte Windows\-Steuerelemente aktivieren, indem Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A>\-Eigenschaft auf `true` festlegen oder die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode verwenden.  Weitere Informationen finden Sie unter [Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## Manuelle Verwaltung von gepufferten Grafiken  
 Bei anspruchsvolleren Szenarien mit doppelter Pufferung, wie Animationen oder erweiterter Speicherverwaltung, können Sie mithilfe der .NET Framework\-Klassen Ihre eigene doppelte Pufferungslogik implementieren.  Die Klasse, die für das Zuordnen und Verwalten einzelner Grafikpuffer verantwortlich ist, ist die <xref:System.Drawing.BufferedGraphicsContext>\-Klasse.  Jede Anwendungsdomäne verfügt über eine standardmäßige <xref:System.Drawing.BufferedGraphicsContext>\-Instanz, die die gesamte standardmäßige doppelte Pufferung für die Anwendung verwaltet.  In den meisten Fällen verfügt jede Anwendung nur über eine Anwendungsdomäne, d. h. normalerweise ist jeder Anwendung ein standardmäßiger <xref:System.Drawing.BufferedGraphicsContext> zugeordnet.  <xref:System.Drawing.BufferedGraphicsContext>\-Standardinstanzen werden von der <xref:System.Drawing.BufferedGraphicsManager>\-Klasse verwaltet.  Sie können einen Verweis auf die standardmäßige <xref:System.Drawing.BufferedGraphicsContext>\-Instanz abrufen, indem Sie die [BufferedGraphicsManager.Current\-Eigenschaft](frlrfSystemDrawingBufferedGraphicsManagerClassCurrentTopic) aufrufen.  Sie können auch eine dedizierte <xref:System.Drawing.BufferedGraphicsContext>\-Instanz erstellen, die die Leistung von grafisch anspruchsvollen Anwendungen verbessern kann.  Informationen über die Erstellung einer <xref:System.Drawing.BufferedGraphicsContext>\-Instanz finden Sie unter [Gewusst wie: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## Manuelles Anzeigen von gepufferten Grafiken  
 Sie können eine Instanz der <xref:System.Drawing.BufferedGraphicsContext>\-Klasse verwenden, um Grafikpuffer zu erstellen, indem Sie die [BufferedGraphicsContext.Allocate\-Methode](frlrfSystemDrawingBufferedGraphicsContextClassAllocateTopic) aufrufen, die eine Instanz der <xref:System.Drawing.BufferedGraphics>\-Klasse zurückgibt.  Das <xref:System.Drawing.BufferedGraphics>\-Objekt verwaltet einen Arbeitsspeicherpuffer, der mit einer Renderingoberfläche verknüpft ist, beispielsweise ein Formular oder ein Steuerelement.  
  
 Nach der Instanziierung verwaltet die <xref:System.Drawing.BufferedGraphics>\-Klasse das Rendering an einen Grafikpuffer im Arbeitsspeicher.  Sie können Grafiken mithilfe der [BufferedGraphics.Graphics\-Eigenschaft](frlrfSystemDrawingBufferedGraphicsClassGraphicsTopic) in den Arbeitsspeicherpuffer rendern, wodurch ein <xref:System.Drawing.Graphics>\-Objekt verfügbar gemacht wird, das dem Arbeitsspeicherpuffer direkt entspricht.  Sie können in dieses <xref:System.Drawing.Graphics>\-Objekt ebenso zeichnen wie in ein <xref:System.Drawing.Graphics>\-Objekt, das eine Zeichenoberfläche darstellt.  Nachdem alle Grafiken in den Puffer gezeichnet wurden, können Sie die [BufferedGraphics.Render\-Methode](frlrfSystemDrawingBufferedGraphicsClassRenderTopic) verwenden, um den Inhalt des Puffers in die Zeichenoberfläche auf dem Bildschirm zu kopieren.  
  
 Weitere Informationen über die Verwendung der <xref:System.Drawing.BufferedGraphics>\-Klasse finden Sie unter [Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md).  Weitere Informationen zum Rendern von Grafiken finden Sie unter [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md).  
  
## Siehe auch  
 <xref:System.Drawing.BufferedGraphics>   
 <xref:System.Drawing.BufferedGraphicsContext>   
 <xref:System.Drawing.BufferedGraphicsManager>   
 [Gewusst wie: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)   
 [Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)   
 [Gewusst wie: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)