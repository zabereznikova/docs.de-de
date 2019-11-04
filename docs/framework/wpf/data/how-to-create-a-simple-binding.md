---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453507"
---
# <a name="how-to-create-a-simple-binding"></a>Gewusst wie: Erstellen einer einfachen Bindung
In diesem Beispiel wird gezeigt, wie ein einfaches <xref:System.Windows.Data.Binding>erstellt wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verfügen Sie über ein `Person`-Objekt mit einer Zeichen folgen Eigenschaft namens `PersonName`. Das `Person`-Objekt wird im Namespace mit dem Namen `SDKSample`definiert.  
  
 Die hervorgehobene Zeile, die das `<src>` Element im folgenden Beispiel enthält, instanziiert das `Person`-Objekt mit dem `PersonName`-Eigenschafts Wert `Joe`. Dies erfolgt im `Resources` Abschnitt, und es wurde ein `x:Key`zugewiesen.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Die markierte Zeile, die das `<TextBlock>` Element enthält, bindet dann das <xref:System.Windows.Controls.TextBlock>-Steuerelement an die `PersonName`-Eigenschaft. Folglich wird die <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
