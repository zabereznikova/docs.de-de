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
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458843"
---
# <a name="how-to-create-a-binding-in-code"></a>Gewusst wie: Erstellen einer Bindung in Code
In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Data.Binding> im Code erstellt und festgelegt wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.FrameworkElement>-Klasse und die <xref:System.Windows.FrameworkContentElement>-Klasse machen beide eine `SetBinding`-Methode verfügbar. Wenn Sie ein Element binden, das eine dieser Klassen erbt, können Sie die <xref:System.Windows.FrameworkElement.SetBinding%2A>-Methode direkt aufzurufen.  
  
 Im folgenden Beispiel wird eine Klasse mit dem Namen `MyData`erstellt, die eine Eigenschaft mit dem Namen `MyDataProperty`enthält.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein Bindungs Objekt erstellt wird, um die Quelle der Bindung festzulegen.  Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> verwendet, um die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft von `myText`, die ein <xref:System.Windows.Controls.TextBlock> Steuerelement ist, an `MyDataProperty`zu binden.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Das Codebeispiel für den gesamten Code finden Sie unter Beispiel für reine [Code Bindung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Anstatt <xref:System.Windows.FrameworkElement.SetBinding%2A>aufrufen zu können, können Sie die <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statische Methode der <xref:System.Windows.Data.BindingOperations>-Klasse verwenden. Im folgenden Beispiel wird <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> aufgerufen, um `myText` an `myDataProperty`zu binden.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
