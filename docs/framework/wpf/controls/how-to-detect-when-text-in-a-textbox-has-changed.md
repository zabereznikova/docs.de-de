---
title: "Gewusst wie: Erkennen von &#196;nderungen an Text in einem Textfeld | Microsoft Docs"
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
  - "Erkennen von Textänderungen"
  - "Textänderungen, Ermitteln"
  - "TextBox-Steuerelement, Erkennen von Textänderungen"
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erkennen von &#196;nderungen an Text in einem Textfeld
In diesem Beispiel wird veranschaulicht, wie mit dem <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Ereignis eine Methode ausgeführt werden kann, wenn sich der Text in einem <xref:System.Windows.Controls.TextBox>\-Steuerelement geändert hat.  
  
 Fügen Sie in der Code\-Behind\-Klasse für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in dem das zu überwachende <xref:System.Windows.Controls.TextBox>\-Steuerelement enthalten ist, eine Methode ein, die immer dann aufgerufen wird, wenn das <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Ereignis ausgelöst wird.  Diese Methode muss über eine Signatur verfügen, die der Erwartung des <xref:System.Windows.Controls.TextChangedEventHandler>\-Delegaten entspricht.  
  
 Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox>\-Steuerelements entweder durch einen Benutzer oder programmgesteuert geändert wird.  
  
 **Hinweis:** Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox>\-Steuerelement erstellt und erstmals mit Text aufgefüllt wird.  
  
## Beispiel  
 Geben Sie im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], mit dem das <xref:System.Windows.Controls.TextBox>\-Steuerelement definiert wird, das <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Attribut mit einem Wert an, der dem Methodennamen des Ereignishandlers entspricht.  
  
 [!code-xml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## Beispiel  
 Fügen Sie in der Code\-Behind\-Klasse für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in dem das zu überwachende <xref:System.Windows.Controls.TextBox>\-Steuerelement enthalten ist, eine Methode ein, die immer dann aufgerufen wird, wenn das <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>\-Ereignis ausgelöst wird.  Diese Methode muss über eine Signatur verfügen, die der Erwartung des <xref:System.Windows.Controls.TextChangedEventHandler>\-Delegaten entspricht.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Der Ereignishandler wird immer dann aufgerufen, wenn der Inhalt des <xref:System.Windows.Controls.TextBox>\-Steuerelements entweder durch einen Benutzer oder programmgesteuert geändert wird.  
  
 **Hinweis:** Dieses Ereignis wird ausgelöst, wenn das <xref:System.Windows.Controls.TextBox>\-Steuerelement erstellt und erstmals mit Text aufgefüllt wird.  
  
 Kommentare  
  
## Siehe auch  
 <xref:System.Windows.Controls.TextChangedEventArgs>   
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)