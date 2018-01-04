---
title: "Gewusst wie: Löschen von Bindungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af45d504eb4e7d45808f787925a90c8e0ed19476
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-bindings"></a>Gewusst wie: Löschen von Bindungen
Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.  
  
## <a name="example"></a>Beispiel  
 Um eine Bindung aus einer einzelnen Eigenschaft für ein Objekt zu löschen, rufen <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> wie im folgenden Beispiel gezeigt. Im folgende Beispiel entfernt die Bindung aus der <xref:System.Windows.Controls.TextBlock.TextProperty> von *Mytext*ein <xref:System.Windows.Controls.TextBlock> Objekt.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt. Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.  
  
 Verwenden, um Bindungen aus allen möglichen Eigenschaften für ein Objekt zu löschen, <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.BindingOperations>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
