---
title: 'Vorgehensweise: Implementieren einer Abhängigkeitseigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 6f2fb9b0824feb6253527de063f58da2427d0c06
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400356"
---
# <a name="how-to-implement-a-dependency-property"></a>Vorgehensweise: Implementieren einer Abhängigkeitseigenschaft
In diesem Beispiel wird gezeigt, wie Sie eine Common Language Runtime (CLR)- <xref:System.Windows.DependencyProperty> Eigenschaft mit einem Feld sichern und so eine Abhängigkeits Eigenschaft definieren. Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zuerst eine Abhängigkeits Eigenschaft durch Aufrufen <xref:System.Windows.DependencyProperty.Register%2A> der-Methode registriert. Der Name des Bezeichnerfelds, das Sie verwenden, um den Namen und die Merkmale der Abhängigkeits Eigenschaft zu <xref:System.Windows.DependencyProperty.Name%2A> speichern, muss das sein, das Sie für die <xref:System.Windows.DependencyProperty.Register%2A> Abhängigkeits Eigenschaft als Teil des Aufrufens ausgewählt haben `Property`. Wenn Sie beispielsweise eine Abhängigkeits Eigenschaft mit einem <xref:System.Windows.DependencyProperty.Name%2A> von `Location`registrieren, muss das Bezeichnerfeld, das Sie für die Abhängigkeits Eigenschaft definieren `LocationProperty`, benannt werden.  
  
 `State`In diesem Beispiel ist der Name der Abhängigkeits Eigenschaft und der zugehörige CLR-Accessor. Das Bezeichnerfeld ist `StateProperty`, der Typ der <xref:System.Boolean>Eigenschaft ist, und der Typ, der die Abhängigkeits Eigenschaft registriert, ist. `MyStateControl`  
  
 Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.  
  
 Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben. Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Weitere Informationen darüber, wie und warum eine Abhängigkeits Eigenschaft implementiert wird, anstatt nur eine CLR-Eigenschaft mit einem privaten Feld zu unterstützen, finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Themen zu Vorgehensweisen](properties-how-to-topics.md)
