---
title: "Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung f&#252;r Formulare und Steuerelemente | Microsoft Docs"
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
  - "DoubleBuffered-Eigenschaft"
  - "Flimmern, Vermindern in Windows Forms"
  - "Grafiken, Vermindern des Flimmerns durch doppelte Pufferung"
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung f&#252;r Formulare und Steuerelemente
Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben.  Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert.  Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert.  Da auf dem Bildschirm nur ein einzelner Grafikvorgang ausgeführt wird, tritt das bei komplexen Zeichenvorgängen übliche Bildflimmern nicht mehr auf. Bei den meisten Anwendungen bietet die standardmäßige doppelte Pufferung von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] optimale Ergebnisse.  Herkömmliche Windows Forms\-Steuerelemente sind standardmäßig doppelt gepuffert.  Sie können die standardmäßige doppelte Pufferung in den Formularen und erstellten Steuerelementen auf zwei Weisen aktivieren.  Sie können entweder die <xref:System.Windows.Forms.Control.DoubleBuffered%2A>\-Eigenschaft auf `true` festlegen oder die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode aufrufen, um das <xref:System.Windows.Forms.ControlStyles>\-Flag auf `true` festzulegen.  Mit beiden Methoden wird die standardmäßige doppelte Pufferung für das Formular bzw. Steuerelement eingerichtet und flimmerfreies Grafikrendering ermöglicht.  Das Aufrufen der <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode empfiehlt sich nur für benutzerdefinierte Steuerelemente, für die Sie den gesamten Renderingcode geschrieben haben.  
  
 Bei anspruchsvolleren Szenarien zur doppelten Pufferung, wie Animationen oder erweitere Speicherverwaltung, können Sie Ihre eigene doppelte Pufferungslogik implementieren.  Weitere Informationen finden Sie unter [Gewusst wie: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### So reduzieren Sie das Flimmern  
  
-   Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A>\-Eigenschaft auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- oder \-  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode auf, um das <xref:System.Windows.Forms.ControlStyles>\-Flag auf `true` festzulegen.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>   
 <xref:System.Windows.Forms.Control.SetStyle%2A>   
 [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)