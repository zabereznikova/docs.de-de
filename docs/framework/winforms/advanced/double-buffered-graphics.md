---
title: Doppelt gepufferte Grafiken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7e4445b0a729eb1f826d17340db02f0c56149b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="double-buffered-graphics"></a>Doppelt gepufferte Grafiken
Flimmern ist ein häufiges Problem beim Programmieren von Grafiken. Grafikoperationen, die mehrere komplexe Zeichenvorgänge erfordern, können dazu führen, dass gerenderte Bilder flimmern oder anderweitig nicht ordnungsgemäß dargestellt werden. Um diese Probleme zu beheben, stellt .NET Framework Zugriff auf doppelte Pufferung bereit.  
  
 Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben. Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert. Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert. Da auf dem Bildschirm nur eine Grafikoperation ausgeführt wird, wird das durch komplexe Zeichenoperationen ausgelöste Bildflimmern beseitigt.  
  
## <a name="default-double-buffering"></a>Standardmäßige doppelte Pufferung  
 Die einfachste Möglichkeit, die doppelte Pufferung in Anwendungen zu verwenden, bietet die doppelte Pufferung für Formulare und Steuerelemente, die standardmäßig von .NET Framework bereitgestellt wird. Sie können standardmäßige doppelte Pufferung für Windows Forms und erstellte Windows-Steuerelemente durch Festlegen der <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft, um `true` oder mithilfe der <xref:System.Windows.Forms.Control.SetStyle%2A> Methode. Weitere Informationen finden Sie unter [Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## <a name="manually-managing-buffered-graphics"></a>Manuelles Verwalten gepufferter Grafiken  
 Bei anspruchsvolleren Szenarien mit doppelter Pufferung, wie Animationen oder erweiterter Speicherverwaltung, können Sie mithilfe der .NET Framework-Klassen Ihre eigene doppelte Pufferungslogik implementieren. Die Klasse, die verantwortlich für das zuordnen und Verwalten einzelner Grafikpuffer ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse. Jede Anwendungsdomäne verfügt über einen eigenen Standard <xref:System.Drawing.BufferedGraphicsContext> -Instanz, die alle Standardeinstellungen, die doppelte Pufferung für die Anwendung verwaltet. In den meisten Fällen werden nur eine Anwendungsdomäne pro Anwendung, daher in der Regel einem standardmäßigen besteht <xref:System.Drawing.BufferedGraphicsContext> pro Anwendung. Standard <xref:System.Drawing.BufferedGraphicsContext> Instanzen werden vom verwaltet die <xref:System.Drawing.BufferedGraphicsManager> Klasse. Sie können einen Verweis auf die Standardwerte abrufen <xref:System.Drawing.BufferedGraphicsContext> Instanz durch Aufrufen der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>. Sie können auch eine dedizierte erstellen <xref:System.Drawing.BufferedGraphicsContext> -Instanz, die Leistung für grafisch anspruchsvolle Anwendungen verbessern kann. Informationen zum Erstellen einer <xref:System.Drawing.BufferedGraphicsContext> Instanz ist, finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Manuelles Anzeigen gepufferter Grafiken  
 Können Sie eine Instanz von der <xref:System.Drawing.BufferedGraphicsContext> -Klasse zum Erstellen von Grafikpuffern durch Aufrufen der <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>, womit eine Instanz von der <xref:System.Drawing.BufferedGraphics> Klasse. Ein <xref:System.Drawing.BufferedGraphics> Objekt verwaltet einen Arbeitsspeicherpuffer, der eine Darstellungsoberfläche, z. B. eines Formulars oder Steuerelements zugeordnet ist.  
  
 Nachdem er instanziiert wird, die <xref:System.Drawing.BufferedGraphics> Klasse verwaltet das Rendering an einen Grafikpuffer im Arbeitsspeicher. Können Sie Grafiken, über die Speicherpuffer Rendern der <xref:System.Drawing.BufferedGraphics.Graphics%2A>, welche macht eine <xref:System.Drawing.Graphics> Objekt, das direkt Speicherpuffer darstellt. Sie können zu diesem <xref:System.Drawing.Graphics> Objekt wie auf ein <xref:System.Drawing.Graphics> Objekt, das eine Zeichenoberfläche darstellt. Nachdem alle Grafiken in den Puffer gezeichnet wurden, können Sie mithilfe der <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> So kopieren Sie den Inhalt des Puffers auf die Zeichenoberfläche auf dem Bildschirm.  
  
 Weitere Informationen zur Verwendung der <xref:System.Drawing.BufferedGraphics> Klasse, finden Sie unter [Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md). Weitere Informationen zum Rendern von Grafiken finden Sie unter [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [Gewusst wie: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [Gewusst wie: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
