---
title: Doppelt gepufferte Grafiken
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: 71463d7db6ae18a3dd21d6a467f3963d836fc086
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707702"
---
# <a name="double-buffered-graphics"></a>Doppelt gepufferte Grafiken
Flimmern ist ein häufiges Problem beim Programmieren von Grafiken. Grafikoperationen, die mehrere komplexe Zeichenvorgänge erfordern, können dazu führen, dass gerenderte Bilder flimmern oder anderweitig nicht ordnungsgemäß dargestellt werden. Um diese Probleme zu beheben, stellt .NET Framework Zugriff auf doppelte Pufferung bereit.  
  
 Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben. Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert. Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert. Da auf dem Bildschirm nur eine Grafikoperation ausgeführt wird, wird das durch komplexe Zeichenoperationen ausgelöste Bildflimmern beseitigt.  
  
## <a name="default-double-buffering"></a>Standardmäßige doppelte Pufferung  
 Die einfachste Möglichkeit, die doppelte Pufferung in Anwendungen zu verwenden, bietet die doppelte Pufferung für Formulare und Steuerelemente, die standardmäßig von .NET Framework bereitgestellt wird. Sie können standardmäßige doppelte Pufferung für Windows Forms und erstellte Windows-Steuerelemente durch Festlegen der <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` oder mithilfe der <xref:System.Windows.Forms.Control.SetStyle%2A> Methode. Weitere Informationen finden Sie unter [Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## <a name="manually-managing-buffered-graphics"></a>Manuelles Verwalten gepufferter Grafiken  
 Bei anspruchsvolleren Szenarien mit doppelter Pufferung, wie Animationen oder erweiterter Speicherverwaltung, können Sie mithilfe der .NET Framework-Klassen Ihre eigene doppelte Pufferungslogik implementieren. Die Klasse, die für das zuordnen und Verwalten einzelner Grafikpuffer verantwortlich ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse. Jede Anwendungsdomäne verfügt über einen standardmäßigen <xref:System.Drawing.BufferedGraphicsContext> -Instanz, die gesamte standardmäßige doppelte Pufferung für die Anwendung verwaltet. In den meisten Fällen stehen nur eine Anwendungsdomäne pro Anwendung, daher in der Regel einem standardmäßigen besteht <xref:System.Drawing.BufferedGraphicsContext> pro Anwendung. Standard <xref:System.Drawing.BufferedGraphicsContext> Instanzen verwaltet werden, indem die <xref:System.Drawing.BufferedGraphicsManager> Klasse. Sie können einen Verweis auf die Standardwerte abrufen <xref:System.Drawing.BufferedGraphicsContext> -Instanz durch Aufrufen der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>. Sie können auch eine dedizierte erstellen <xref:System.Drawing.BufferedGraphicsContext> -Instanz, die Leistung von grafisch anspruchsvollen Anwendungen verbessern kann. Informationen zum Erstellen einer <xref:System.Drawing.BufferedGraphicsContext> Instanz ist, finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Manuelles Anzeigen gepufferter Grafiken  
 Können Sie eine Instanz von der <xref:System.Drawing.BufferedGraphicsContext> Klasse, um Grafikpuffer zu erstellen, indem die <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>, womit eine Instanz von der <xref:System.Drawing.BufferedGraphics> Klasse. Ein <xref:System.Drawing.BufferedGraphics> Objekt verwaltet einen Arbeitsspeicherpuffer, der mit einer Renderingoberfläche, z. B. einem Formular oder Steuerelement zugeordnet ist.  
  
 Nachdem er instanziiert wird, die <xref:System.Drawing.BufferedGraphics> Klasse verwaltet das Rendering an einen Grafikpuffer im Arbeitsspeicher. Sie können Rendern von Grafiken in den Arbeitsspeicherpuffer über die <xref:System.Drawing.BufferedGraphics.Graphics%2A>, verfügbar macht eine <xref:System.Drawing.Graphics> Objekt, das dem Arbeitsspeicherpuffer direkt darstellt. Sie können auf dieses zeichnen <xref:System.Drawing.Graphics> Objekt genau wie auf eine <xref:System.Drawing.Graphics> -Objekt, das eine Zeichenoberfläche darstellt. Nachdem alle Grafiken in den Puffer gezeichnet wurden, können Sie mithilfe der <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> um den Inhalt des Puffers auf die Zeichenoberfläche auf dem Bildschirm zu kopieren.  
  
 Weitere Informationen zur Verwendung der <xref:System.Drawing.BufferedGraphics> Klasse, finden Sie unter [Manuelles Rendern von gepufferten Grafiken](how-to-manually-render-buffered-graphics.md). Weitere Informationen zum Rendern von Grafiken finden Sie unter [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.BufferedGraphics>
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphicsManager>
- [Vorgehensweise: Manuelles Rendern von gepufferten Grafiken](how-to-manually-render-buffered-graphics.md)
- [Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)
- [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
