---
title: "Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Zeichnen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Rendern"
  - "OnPaint-Methode"
  - "Benutzersteuerelemente [Windows Forms], Zeichnen"
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
Das benutzerdefinierte Zeichnen von Steuerelementen stellt eine der vielen anspruchsvollen Aufgaben dar, die durch .NET Framework vereinfacht werden.  Beim Erstellen eines benutzerdefinierten Steuerelements bestehen viele Möglichkeiten zu seiner grafischen Darstellung.  Wenn ein Steuerelement erstellt wird, das von `Control` erbt, muss Code bereitgestellt werden. Damit wird dem Steuerelement ermöglicht, seine grafische Darstellung zu rendern.  Wenn ein Benutzersteuerelement durch Erben von `UserControl` erstellt oder von einem der Steuerelemente in Windows Forms geerbt wird, darf die standardmäßige Grafikdarstellung überschrieben werden, um eigenen Grafikcode bereitzustellen.  Wenn für die einzelnen Steuerelemente eines erstellten `UserControl` benutzerdefiniertes Rendern bereitgestellt werden soll, sind die Optionen etwas eingeschränkter. Es stehen jedoch weiterhin zahlreiche Grafikfunktionen für die Steuerelemente und Anwendungen zur Verfügung.  
  
## In diesem Abschnitt  
 [Wiedergeben eines Windows Forms\-Steuerelements](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Zeigt das Programmieren der Logik, durch die ein Steuerelement angezeigt wird.  
  
 [Benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Bietet eine Übersicht über die Schritte, die in das Schreiben und Überschreiben von Code zum Rendern des Steuerelements einbezogen sind.  
  
 [Konstituierende Steuerelemente](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Beschreibt, wie benutzerdefinierter Code zum Rendern konstituierender Steuerelemente in Benutzersteuerelementen und Formularen implementiert wird.  
  
 [Gewusst wie: Ausblenden des Steuerelements zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Veranschaulicht die Verwendung der <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft zum Ausblenden und Anzeigen eines Steuerelements.  
  
 [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Veranschaulicht die Verwendung der <xref:System.Windows.Forms.Control.SetStyle%2A>\-Methode zum Erstellen einer Hintergrundfarbe, die nicht transparent, transparent oder teilweise transparent ist.  
  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Veranschaulicht, wie Steuerelemente mit visuellen Stilen in Betriebssystemen gerendert werden, die diese unterstützen.  
  
## Referenz  
 <xref:System.Windows.Forms.Control>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.UserControl>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Beschreibt diese Methode.  
  
## Verwandte Abschnitte  
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Stellt die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]\-Grafikfunktionalität aus einer Visual Studio\-Perspektive vor und enthält Links zu weiteren Informationen.  
  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Beschreibt die Arten von benutzerdefinierten Steuerelementen, die Sie erstellen können.