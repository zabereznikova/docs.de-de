---
title: "Gewusst wie: Implementieren von Validierungslogik f&#252;r benutzerdefinierte Objekte | Microsoft Docs"
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
  - "Überprüfen auf Fehler bei der Validierung [WPF]"
  - "Benutzerdefinierte Objekte [WPF], Implementieren von Validierungslogik für"
  - "Implementieren von Validierungslogik für benutzerdefinierte Objekte [WPF]"
  - "Validierungsfehler [WPF], Überprüfen auf"
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Implementieren von Validierungslogik f&#252;r benutzerdefinierte Objekte
In diesem Beispiel wird gezeigt, wie Sie Validierungslogik für ein benutzerdefiniertes Objekt implementieren und anschließend daran binden.  
  
## Beispiel  
 Sie können Validierungslogik auf der Geschäftsebene zur Verfügung stellen, wenn das Quellobjekt <xref:System.ComponentModel.IDataErrorInfo> implementiert, wie im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Im folgenden Beispiel wird die Texteigenschaft des Textfeldes an die `Age`\-Eigenschaft des `Person`\-Objekts gebunden, das für die Bindung über eine in `x:Key` `data` angegebene Ressourcendeklaration zur Verfügung gestellt wurde.  <xref:System.Windows.Controls.DataErrorValidationRule> sucht von der <xref:System.ComponentModel.IDataErrorInfo>\-Implementierung ausgelöste Validierungsfehler.  
  
 [!code-xml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Alternativ zur Verwendung von <xref:System.Windows.Controls.DataErrorValidationRule> können Sie die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>\-Eigenschaft auf `true` festlegen.  
  
## Siehe auch  
 <xref:System.Windows.Controls.ExceptionValidationRule>   
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)