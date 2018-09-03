---
title: 'Gewusst wie: Erstellen einer Bindung in Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483020"
---
# <a name="how-to-create-a-binding-in-code"></a>Gewusst wie: Erstellen einer Bindung in Code
Dieses Beispiel veranschaulicht das Erstellen und Festlegen einer <xref:System.Windows.Data.Binding> im Code.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.FrameworkElement> Klasse und die <xref:System.Windows.FrameworkContentElement> Klasse, die beide verfügbar machen, eine `SetBinding` Methode. Wenn Sie ein Element, die eine dieser Klassen erbt binden, können Sie rufen die <xref:System.Windows.FrameworkElement.SetBinding%2A> -Methode direkt.  
  
 Das folgende Beispiel erstellt eine Klasse, die mit dem Namen `MyData`, enthält eine Eigenschaft namens `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Das folgende Beispiel zeigt, wie Sie erstellen ein Binding-Objekt, um die Quelle der Bindung festgelegt wird.  Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> zum Binden der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft `myText`, d.h. eine <xref:System.Windows.Controls.TextBlock> Steuerelements, auf `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Das vollständige Codebeispiel finden Sie unter [nur ein Beispiel für die Bindung](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).  
  
 Statt <xref:System.Windows.FrameworkElement.SetBinding%2A>, können Sie die <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statische Methode der <xref:System.Windows.Data.BindingOperations> Klasse. Das folgende Beispiel auszuführen, ruft <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> binden `myText` zu `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
