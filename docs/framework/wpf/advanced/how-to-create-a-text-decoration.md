---
title: "Gewusst wie: Erstellen einer Textdekoration | Microsoft Docs"
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
  - "Baseline-Typ"
  - "Schriftarten, Baseline"
  - "Schriftarten, Überstrich"
  - "Schriftarten, Durchgestrichen"
  - "Schriftarten, Unterstrich"
  - "Überstrich-Typ"
  - "Durchgestrichen-Typ"
  - "Text, Ergänzungen"
  - "Typografie, Textergänzungen"
  - "Unterstrich-Typ"
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen einer Textdekoration
Ein <xref:System.Windows.TextDecoration>\-Objekt ist eine visuelle Verzierung, die dem Text hinzugefügt werden kann.  Es gibt vier Typen von Textdekorationen: Unterstrichen, Baseline, Durchgestrichen und Überstrichen.  Im folgenden Beispiel werden die Positionen der Textdekorationen relativ zum Text dargestellt.  
  
 ![Diagramm der Textergänzungsstellen](../../../../docs/framework/wpf/advanced/media/textdecoration01.png "TextDecoration01")  
Beispiel für Textdekorationstypen  
  
 Um Text eine Textdekoration hinzuzufügen, erstellen Sie ein <xref:System.Windows.TextDecoration>\-Objekt, und ändern Sie seine Eigenschaften.  Verwenden Sie die <xref:System.Windows.TextDecoration.Location%2A>\-Eigenschaft, um anzugeben, wo die Textdekoration angezeigt wird, z. B. Unterstrich.  Verwenden Sie die <xref:System.Windows.TextDecoration.Pen%2A>\-Eigenschaft, um die Darstellung der Textdekoration anzugeben, z. B. eine Volltonfüllung oder ein Farbverlauf.  Wenn Sie keinen Wert für die <xref:System.Windows.TextDecoration.Pen%2A>\-Eigenschaft angeben, übernehmen die Dekorationen standardmäßig die Textfarbe.  Nachdem Sie ein <xref:System.Windows.TextDecoration>\-Objekt definiert haben, fügen Sie es zur <xref:System.Windows.TextDecorations>\-Auflistung des gewünschten Textobjekts hinzu.  
  
 Im folgenden Beispiel wird eine Textdekoration gezeigt, die mit einem Pinsel für lineare Verläufe und einem gestrichelten Stift formatiert wurde.  
  
 ![Textergänzung mit linearer Farbverlaufsunterstreichung](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
Beispiel für eine Unterstreichung mithilfe eines Pinsels für lineare Verläufe und eines gestrichelten Stifts  
  
 Das <xref:System.Windows.Documents.Hyperlink>\-Objekt stellt ein fortlaufendes Inhaltselement auf Inlineebene dar, das Ihnen das Hosten von Links im fortlaufenden Inhalt ermöglicht.  Standardmäßig verwendet <xref:System.Windows.Documents.Hyperlink> ein <xref:System.Windows.TextDecoration>\-Objekt, um eine Unterstreichung anzuzeigen.  Die Instanziierung von <xref:System.Windows.TextDecoration>\-Objekten kann ressourcenintensiv sein, insbesondere bei vielen <xref:System.Windows.Documents.Hyperlink>\-Objekten.  Wenn Sie <xref:System.Windows.Documents.Hyperlink>\-Elemente häufig einsetzen, sollten Sie einen Unterstrich nur anzeigen, wenn Sie ein Ereignis, z. B. das <xref:System.Windows.ContentElement.MouseEnter>\-Ereignis, auslösen.  
  
 Im folgenden Beispiel ist der Unterstrich für den Link "My MSN" dynamisch. Er wird nur angezeigt, wenn das <xref:System.Windows.ContentElement.MouseEnter>\-Ereignis ausgelöst wird.  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Mit Textdekorationen definierte Links  
  
 Weitere Informationen finden Sie unter [Angeben, ob ein Hyperlink unterstrichen wird](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## Beispiel  
 Im folgenden Codebeispiel wird für eine unterstrichene Textdekoration der Standardschriftartwert verwendet.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Im folgenden Codebeispiel wird eine Textdekoration für Unterstreichung mit einem Volltonfarbenpinsel für den Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Im folgenden Codebeispiel wird eine Textdekoration für Unterstreichungen mithilfe eines Pinsels für lineare Verläufe für den gestrichelten Stift erstellt.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## Siehe auch  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Angeben, ob ein Hyperlink unterstrichen wird](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)