---
title: "Gewusst wie: Erstellen von Text mit Kontur | Microsoft Docs"
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
  - "Farbverlaufspinsel"
  - "Linearer Farbverlaufspinsel"
  - "Unterstrichener Text"
  - "Typografie, Linearer Farbverlaufspinsel"
  - "Typografie, Gliederungseffekte"
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen von Text mit Kontur
Wenn Sie Textzeichenfolgen in einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendung mit Verzierungen versehen, verwenden Sie in den meisten Fällen Text in Form einer Auflistung diskreter Zeichen oder Symbole.  Sie können beispielsweise einen Pinsel mit linearem Farbverlauf erstellen und auf die <xref:System.Windows.Controls.Control.Foreground%2A>\-Eigenschaft eines <xref:System.Windows.Controls.TextBox>\-Objekts anwenden.  Wenn Sie das Textfeld anzeigen oder bearbeiten, wird der Pinsel mit linearem Farbverlauf automatisch auf den aktuellen Satz von Zeichen in der Textzeichenfolge angewendet.  
  
 ![Angezeigter Text mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext01.png "OutlinedText01")  
  
        Beispiel für die Anwendung eines Pinsel mit linearem Farbverlauf auf ein Textfeld  
  
 Sie können Text aber auch in <xref:System.Windows.Media.Geometry>\-Objekte umwandeln, sodass Sie andere optisch vielfältige Textarten erstellen können.  Sie können beispielsweise auf Grundlage der Gliederung einer Textzeichenfolge ein <xref:System.Windows.Media.Geometry>\-Objekt erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
  
        Beispiel für die Anwendung eines Pinsels mit linearem Farbverlauf auf die Konturgeometrie von Text  
  
 Wenn Text in ein <xref:System.Windows.Media.Geometry>\-Objekt konvertiert wird, handelt es sich nicht mehr um eine Auflistung von Zeichen. Sie können die Zeichen in der Zeichenfolge nicht mehr ändern.  Sie können jedoch die Darstellung des konvertierten Texts beeinflussen, indem Sie dessen Stricheigenschaften und Fülleigenschaften ändern.  Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur des konvertierten Texts.  
  
 In den folgenden Beispielen werden mehrere Verfahren zum Erstellen visueller Effekte durch Ändern des Strichs und der Füllung von konvertiertem Text veranschaulicht.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
  
        Beispiel für das Festlegen von verschiedenen Farben für Striche und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
  
        Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 Es ist auch möglich, das umgebende Feldrechteck oder die Hervorhebung des konvertierten Texts zu ändern.  Im folgenden Beispiel wird das Erstellen visueller Effekte durch Ändern des Strichs und der Hervorhebung von konvertiertem Text veranschaulicht.  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
## Beispiel  
 Der Schlüssel bei der Konvertierung von Text in ein <xref:System.Windows.Media.Geometry>\-Objekt liegt in der Verwendung des <xref:System.Windows.Media.FormattedText>\-Objekts.  Nachdem Sie dieses Objekt erstellt haben, können Sie den Text mit den Methoden <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> und <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> in <xref:System.Windows.Media.Geometry>\-Objekte konvertieren.  Die erste Methode gibt die Geometrie des formatierten Texts zurück und die zweite Methode die Geometrie des Felds, das den formatierten Text umgibt.  Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Media.FormattedText>\-Objekt erstellen, und wie Sie die Geometrien des formatierten Texts sowie seines umgebenden Felds abrufen.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Um die abgerufenen <xref:System.Windows.Media.Geometry>\-Objekte anzuzeigen, müssen Sie auf den <xref:System.Windows.Media.DrawingContext> des Objekts zugreifen, das den konvertierten Text anzeigt.  In diesen Codebeispielen wird dazu ein benutzerdefiniertes Steuerelementobjekt erstellt. Dieses Objekt wird von einer Klasse abgeleitet, die benutzerdefiniertes Rendering unterstützt.  
  
 Um <xref:System.Windows.Media.Geometry>\-Objekte im benutzerdefinierten Steuerelement anzuzeigen, stellen Sie eine Überschreibung für die <xref:System.Windows.UIElement.OnRender%2A>\-Methode bereit.  Die überschriebene Methode sollte die <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>\-Methode verwenden, um die <xref:System.Windows.Media.Geometry>\-Objekte zu zeichnen.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## Siehe auch  
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)