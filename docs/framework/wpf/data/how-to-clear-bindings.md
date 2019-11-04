---
title: 'Gewusst wie: Löschen von Bindungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 66f7eb0209d23660b9c7351ca793f509b2f4bb8d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458877"
---
# <a name="how-to-clear-bindings"></a>Gewusst wie: Löschen von Bindungen
Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.  
  
## <a name="example"></a>Beispiel  
 Um eine Bindung aus einer einzelnen Eigenschaft eines Objekts zu löschen, nennen Sie <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>, wie im folgenden Beispiel gezeigt. Im folgenden Beispiel wird die-Bindung aus dem <xref:System.Windows.Controls.TextBlock.TextProperty> von *MyText*entfernt, einem <xref:System.Windows.Controls.TextBlock>-Objekt.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt. Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.  
  
 Um Bindungen aus allen möglichen Eigenschaften eines Objekts zu löschen, verwenden Sie <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.BindingOperations>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
