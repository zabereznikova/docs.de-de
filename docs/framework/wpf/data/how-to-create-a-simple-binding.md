---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
description: Erstellen Sie mithilfe dieser Vorgehensweise in Windows Presentation Foundation (WPF) eine einfache Bindung für Ihre Anwendungen.
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618700"
---
# <a name="how-to-create-a-simple-binding"></a>Gewusst wie: Erstellen einer einfachen Bindung
In diesem Beispiel wird gezeigt, wie ein einfaches erstellt wird <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verfügen Sie über ein- `Person` Objekt mit der Zeichen folgen Eigenschaft `PersonName` . Das- `Person` Objekt wird im-Namespace mit dem Namen definiert `SDKSample` .  
  
 Die markierte Zeile, die das- `<src>` Element im folgenden Beispiel enthält, instanziiert das- `Person` Objekt mit einem- `PersonName` Eigenschafts Wert von `Joe` . Dies erfolgt im `Resources` -Abschnitt und wird zugewiesen `x:Key` .  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Die markierte Zeile, die das-Element enthält, `<TextBlock>` bindet dann das- <xref:System.Windows.Controls.TextBlock> Steuerelement an die- `PersonName` Eigenschaft. Folglich wird der <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
