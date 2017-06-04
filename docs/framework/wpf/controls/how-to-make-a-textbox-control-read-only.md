---
title: "Gewusst wie: Erstellen eines schreibgesch&#252;tzten TextBox-Steuerelements | Microsoft Docs"
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
  - "Schreibgeschützte TextBox-Steuerelemente"
  - "Schreibgeschütztes TextBox-Steuerelement"
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen eines schreibgesch&#252;tzten TextBox-Steuerelements
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.TextBox>\-Steuerelement konfiguriert wird, um keine Benutzereingabe oder Änderung zu ermöglichen.  
  
## Beispiel  
 Um zu verhindern, dass Benutzer den Inhalt eines <xref:System.Windows.Controls.TextBox>\-Steuerelements ändern, legen Sie das <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>\-Attribut auf **true** fest.  
  
 [!code-xml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 Das <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>\-Attribut betrifft nur die Benutzereingabe; es betrifft nicht Text, der in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beschreibung eines <xref:System.Windows.Controls.TextBox>\-Steuerelements festgelegt wird, oder Text, der programmgesteuert über die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft festgelegt wird.  
  
 Der Standardwert von <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> ist **false**.  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)