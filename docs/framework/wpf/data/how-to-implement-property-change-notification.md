---
title: "Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen"
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
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6674628acd4ea6b18f98a0ab5e20935220595de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-property-change-notification"></a>Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen
Zur Unterstützung <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Binden an die Ziel-Bindungseigenschaften automatisch entsprechend der dynamischen Änderungen der Bindungsquelle (z. B. im Vorschaufenster automatisch aktualisiert, wenn der Benutzer ein Formulars bearbeitet haben), aktivieren eine Klasse muss die richtige geänderten Eigenschaft Benachrichtigungen enthalten. In diesem Beispiel wird gezeigt, wie eine Klasse erstellen, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Beispiel  
 Implementiert <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie deklarieren die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis, und erstellen Sie die `OnPropertyChanged` Methode. Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Ein Beispiel gezeigt, wie die `Person` Klasse kann verwendet werden, um Unterstützung <xref:System.Windows.Data.BindingMode.TwoWay> binden, finden Sie unter [steuern, wann der TextBox-Text die Quelle aktualisiert](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
