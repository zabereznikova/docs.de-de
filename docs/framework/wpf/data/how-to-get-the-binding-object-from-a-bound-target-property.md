---
title: "Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft | Microsoft Docs"
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
  - "Datenbindung, Abrufen von Bindungsobjekten aus gebundenen Zieleigenschaften"
  - "Eigenschaften, Abrufen von Bindungsobjekten aus"
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.  
  
## Beispiel  
 Gehen Sie wie folgt vor, um das <xref:System.Windows.Data.Binding>\-Objekt abzurufen:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Sie müssen die [Abhängigkeitseigenschaft](GTMT) für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.  
  
 Alternativ dazu können Sie die <xref:System.Windows.Data.BindingExpression> und danach den Wert der <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>\-Eigenschaft abrufen.  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Wenn die Bindung ein <xref:System.Windows.Data.MultiBinding> ist, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.  Handelt es sich um ein <xref:System.Windows.Data.PriorityBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.  Wenn Sie unsicher sind, ob die Zieleigenschaft anhand von <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding> oder <xref:System.Windows.Data.PriorityBinding> gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A> verwenden.  
  
## Siehe auch  
 [Erstellen einer Bindung in Code](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)