---
title: 'Vorgehensweise: Definieren eines Namensbereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 656c1e9af11697cd4a1253bdab673887765976a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674465"
---
# <a name="how-to-define-a-name-scope"></a>Vorgehensweise: Definieren eines Namensbereichs
Animieren mit <xref:System.Windows.Media.Animation.Storyboard> im Code müssen Sie erstellen eine <xref:System.Windows.NameScope> und registrieren Sie die Namen der Zielobjekte mit dem Element, das diesen Namensbereich besitzt. Im folgenden Beispiel eine <xref:System.Windows.NameScope> für erstellt `myMainPanel`. Zwei Schaltflächen, `button1` und `button2`, Bereich, und ihre registrierten Namen hinzugefügt werden. Mehrere Animationen und <xref:System.Windows.Media.Animation.Storyboard> werden erstellt. Storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode wird verwendet, um die Animationen zu starten.  
  
 Da `button1`, `button2`, und `myMainPanel` all den Gültigkeitsbereich der gleichen Namen verwenden, eines dieser Projekte kann verwendet werden, mit der <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um die Animationen zu starten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>Siehe auch
- [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
