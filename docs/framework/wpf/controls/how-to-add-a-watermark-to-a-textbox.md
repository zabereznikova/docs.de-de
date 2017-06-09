---
title: "Gewusst wie: Hinzuf&#252;gen eines Wasserzeichens zu einer TextBox | Microsoft Docs"
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
  - "Unterstützen der Verwendbarkeit von TextBox mit einem Hintergrundbild [WPF]"
  - "Anzeigen eines Hintergrundbilds in einem Textfeld zur Unterstützung der Benutzereingabe [WPF]"
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Hinzuf&#252;gen eines Wasserzeichens zu einer TextBox
Im folgenden Beispiel wird veranschaulicht, wie die Verwendbarkeit eines <xref:System.Windows.Controls.TextBox> unterstützt wird, indem ein erklärendes Hintergrundbild im <xref:System.Windows.Controls.TextBox> angezeigt wird, bis der Benutzer Text eingibt. Dann wird das Bild entfernt.  Außerdem wird das Hintergrundbild wiederhergestellt, wenn der Benutzer die Eingabe entfernt.  Siehe folgende Abbildung.  
  
 ![Eine TextBox mit einem Hintergrundbild](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing\_TextBox\_using\_background\_image")  
  
> [!NOTE]
>  Der Grund für die Verwendung eines Hintergrundbilds in diesem Beispiel, statt einfach die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft von <xref:System.Windows.Controls.TextBox> zu bearbeiten, ist, dass das Hintergrundbild keine Auswirkungen auf die Datenbindung hat.  
  
## Beispiel  
 [!code-xml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)