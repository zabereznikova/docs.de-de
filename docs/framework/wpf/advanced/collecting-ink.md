---
title: "Erfassen von Freihandeingaben | Microsoft Docs"
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
  - "Erfassen von Freihandeingaben"
  - "DefaultDrawingAttributes-Eigenschaft"
  - "Freihandeingaben, Erfassen"
  - "DrawingAttributes-Eigenschaft"
  - "Freihandeingaben, Erfassen"
  - "InkCanvas-Element"
  - "Eigenschaften, DefaultDrawingAttributes"
  - "Eigenschaften, DrawingAttributes"
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Erfassen von Freihandeingaben
Zu den Kernfunktionen der [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)\-Plattform gehört das Erfassen digitaler Freihandeingaben.  In diesem Thema werden Methoden zum Erfassen von Freihandeingaben in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] erläutert.  
  
## Vorbereitungsmaßnahmen  
 Um die folgenden Beispiele verwenden zu können, müssen Sie zunächst [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] und das [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] installieren.  Sie sollten ebenfalls wissen, wie Anwendungen für den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geschrieben werden.  Weitere Informationen zu den ersten Schritten mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Verwenden des InkCanvas\-Elements  
 Das <xref:System.Windows.Controls.InkCanvas>\-Element bietet die einfachste Möglichkeit, Freihandeingaben in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu erfassen.  Das <xref:System.Windows.Controls.InkCanvas>\-Element ähnelt dem <xref:Microsoft.Ink.InkOverlay>\-Objekt des [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] und früherer Versionen.  
  
 Verwenden Sie ein <xref:System.Windows.Controls.InkCanvas>\-Element, um Freihandeingaben zu empfangen und anzuzeigen.  Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der durch Interaktion mit einem Digitizer Freihandstriche erzeugt.  Außerdem kann eine Maus anstelle eines Tablettstifts verwendet werden.  Die erzeugten Striche werden durch <xref:System.Windows.Ink.Stroke>\-Objekte repräsentiert, die sowohl programmgesteuert als auch durch Benutzereingaben bearbeitet werden können.  Mithilfe von <xref:System.Windows.Controls.InkCanvas> können Benutzer einen vorhandenen <xref:System.Windows.Ink.Stroke> auswählen, ändern oder löschen.  
  
 Mit XAML kann die Erfassung von Freihandeingaben genauso einfach eingerichtet werden, wie ein `InkCanvas`\-Element der Struktur hinzugefügt werden kann.  Im folgenden Beispiel wird ein <xref:System.Windows.Controls.InkCanvas> einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardprojekt hinzugefügt, das in [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] erstellt wurde.  
  
 [!code-xml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 Das `InkCanvas`\-Element kann außerdem untergeordnete Elemente enthalten. Dadurch können beinahe jedem XAML\-Elementtyp Funktionen für Freihandanmerkungen hinzugefügt werden.  So können Sie beispielsweise einem Textelement Freihandfunktionen hinzufügen, indem Sie es zu einem untergeordneten Element eines <xref:System.Windows.Controls.InkCanvas> machen.  
  
 [!code-xml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Ebenso einfach können Sie die Möglichkeit zum Markieren eines Bildes per Freihandeingabe zur Verfügung stellen.  
  
 [!code-xml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### InkCollection\-Modi  
 <xref:System.Windows.Controls.InkCanvas> unterstützt über die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>\-Eigenschaft zahlreiche Eingabemodi.  
  
### Bearbeiten von Freihandeingaben  
 <xref:System.Windows.Controls.InkCanvas> unterstützt viele Freihandbearbeitungsvorgänge.  Beispielsweise unterstützt <xref:System.Windows.Controls.InkCanvas> das Löschen mithilfe des oberen Stiftendes, ohne dass zusätzlicher Code benötigt wird, um dem Element diese Funktionalität hinzuzufügen.  
  
#### Auswahl  
 Der Auswahlmodus wird einfach eingestellt, indem die <xref:System.Windows.Controls.InkCanvasEditingMode>\-Eigenschaft auf **Select** festgelegt wird.  Im folgenden Code wird der Bearbeitungsmodus auf der Grundlage des Werts von <xref:System.Windows.Forms.CheckBox> festgelegt:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### DrawingAttributes  
 Verwenden Sie die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>\-Eigenschaft, um die Darstellung von Freihandstrichen zu ändern.  Zum Beispiel legt der <xref:System.Windows.Ink.DrawingAttributes.Color%2A>\-Member von <xref:System.Windows.Ink.DrawingAttributes> die Farbe vom gerenderten <xref:System.Windows.Ink.Stroke> fest.  Im folgenden Beispiel wird die Farbe der ausgewählten Striche zu Rot geändert.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### DefaultDrawingAttributes  
 Über die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>\-Eigenschaft kann auf Eigenschaften wie Höhe, Breite und Farbe der in einem <xref:System.Windows.Controls.InkCanvas> zu erzeugenden Striche zugegriffen werden.  Sobald Sie die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> geändert haben, werden alle danach in <xref:System.Windows.Controls.InkCanvas> eingegebenen Striche mit den neuen Eigenschaftswerten gerendert.  
  
 Zusätzlich zum Bearbeiten der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in den Code\-Behind\-Dateien können Sie XAML\-Syntax verwenden, um <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>\-Eigenschaften festzulegen.  Im folgenden XAML\-Code wird das Festlegen der <xref:System.Windows.Ink.DrawingAttributes.Color%2A>\-Eigenschaft veranschaulicht.  Erstellen Sie zum Verwenden dieses Codes in Visual Studio 2005 ein neues [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Projekt mit dem Namen "HelloInkCanvas".  Ersetzen Sie den Code in Window1.xaml durch den folgenden Code.  
  
 [!code-xml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 Fügen Sie im nächsten Schritt der Code\-Behind\-Datei folgende Schaltflächen\-Ereignishandler innerhalb der Window1\-Klasse hinzu.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 Nachdem Sie diesen Code kopiert haben, drücken Sie **F5** in Microsoft Visual Studio 2005, um das Programm im Debugger auszuführen.  
  
 Beachten Sie, wie <xref:System.Windows.Controls.StackPanel> die Schaltflächen oben auf <xref:System.Windows.Controls.InkCanvas> platziert.  Wenn Sie versuchen, Freihandeingaben über die Schaltflächen hinweg vorzunehmen, erfasst und rendert <xref:System.Windows.Controls.InkCanvas> diese hinter den Schaltflächen.  Das liegt daran, dass die Schaltflächen, im Gegensatz zu untergeordneten Elementen, nebengeordnete Elemente von <xref:System.Windows.Controls.InkCanvas> sind.  Außerdem befinden sich die Schaltflächen an einer höheren Position in der z\-Reihenfolge. Daher werden die Freihandeingaben hinter ihnen gerendert.  
  
## Siehe auch  
 <xref:System.Windows.Ink.DrawingAttributes>   
 <xref:System.Windows.InkCanvas.DefaultDrawingAttributes%2A>   
 <xref:System.Windows.Ink>