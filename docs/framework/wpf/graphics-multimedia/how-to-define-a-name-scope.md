---
title: 'Gewusst wie: Definieren eines Namensbereichs'
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
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3007088f849f40e4e9b4f1846c19c98c33e95c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-name-scope"></a>Gewusst wie: Definieren eines Namensbereichs
Animieren mit <xref:System.Windows.Media.Animation.Storyboard> in Code, erstellen Sie eine <xref:System.Windows.NameScope> und registrieren Sie die Zielobjekte Namen mit dem Element, diese Namensbereich besitzt. Im folgenden Beispiel ein <xref:System.Windows.NameScope> wird erstellt für `myMainPanel`. Zwei Schaltflächen `button1` und `button2`, Bereich und ihre registrierten Namen hinzugefügt werden. Mehrere Animationen und ein <xref:System.Windows.Media.Animation.Storyboard> erstellt werden. Des Storyboards <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode wird verwendet, um die Animationen zu starten.  
  
 Da `button1`, `button2`, und `myMainPanel` alle den gleichen Namensbereich Teilen, eines dieser kann verwendet werden, mit der <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um die Animationen zu starten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
