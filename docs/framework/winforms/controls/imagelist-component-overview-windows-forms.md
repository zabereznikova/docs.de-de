---
title: "&#220;bersicht &#252;ber die ImageList-Komponente (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ImageList"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Auflistungssteuerelemente, Bilder"
  - "Symbollistensteuerelement"
  - "ImageList-Komponente [Windows Forms], Informationen über die ImageList-Komponente"
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# &#220;bersicht &#252;ber die ImageList-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.ImageList>\-Komponente in Windows Forms wird zum Speichern von Bildern verwendet, die dann von Steuerelementen angezeigt werden können.  Mit einer Bildliste können Sie Code für einen einzelnen, konsistenten Katalog von Bildern schreiben.  So können z. B. Bilder, die durch ein <xref:System.Windows.Forms.Button>\-Steuerelement angezeigt werden, gedreht werden, indem einfach die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>\- oder <xref:System.Windows.Forms.ButtonBase.ImageKey%2A>\-Eigenschaft der Schaltfläche geändert wird.  Dieselbe Bildliste kann auch mit mehreren Steuerelementen verbunden werden.  Wenn z. B. sowohl ein <xref:System.Windows.Forms.ListView>\-Steuerelement als auch ein <xref:System.Windows.Forms.TreeView>\-Steuerelement verwendet werden, um dieselbe Liste von Dateien anzuzeigen, bewirkt eine Änderung des Dateisymbols in der Bildliste, dass das neue Symbol in beiden Ansichten angezeigt wird.  
  
## Verwenden von ImageList mit Steuerelementen  
 Eine Bildliste kann mit jedem Steuerelement eingesetzt werden, das eine `ImageList`\-Eigenschaft aufweist. Wenn jedoch ein <xref:System.Windows.Forms.ListView>\-Steuerelement verwendet wird, muss dieses eine <xref:System.Windows.Forms.ListView.SmallImageList%2A>\-Eigenschaft und eine <xref:System.Windows.Forms.ListView.LargeImageList%2A>\-Eigenschaft aufweisen.  Die folgenden Steuerelemente können mit einer Bildliste verbunden werden: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> und <xref:System.Windows.Forms.Label>.  Legen Sie die `ImageList`\-Eigenschaft des Steuerelements auf den Namen der <xref:System.Windows.Forms.ImageList>\-Komponente fest, um die Bildliste einem Steuerelement zuzuordnen.  
  
## Schlüsseleigenschaften  
 Die wichtigste Eigenschaft der <xref:System.Windows.Forms.ImageList>\-Komponente ist <xref:System.Windows.Forms.ImageList.Images%2A>, in der die Bilder enthalten sind, die vom zugeordneten Steuerelement verwendet werden.  Der Zugriff auf jedes einzelne Bild kann über dessen Indexwert oder dessen Schlüssel erfolgen.  Mit der <xref:System.Windows.Forms.ImageList.ColorDepth%2A>\-Eigenschaft wird die Anzahl der Farben bestimmt, mit denen die Bilder dargestellt werden.  Alle Bilder werden in derselben Größe angezeigt, die durch die <xref:System.Windows.Forms.ImageList.ImageSize%2A>\-Eigenschaft festgelegt ist.  Größere Bilder werden entsprechend angepasst.  
  
 Bei Verwendung von [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] haben Sie Zugriff auf eine umfangreiche Bibliothek von Standardbildern, die Sie in Ihren Anwendungen verwenden können.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ImageList>   
 [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)