---
title: 'Gewusst wie: Implementieren einer Abhängigkeitseigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: b0c5b33d841f43249f9559bd31f1ef8fe66ff05e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544647"
---
# <a name="how-to-implement-a-dependency-property"></a>Gewusst wie: Implementieren einer Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie Sie eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Eigenschaft mit einer <xref:System.Windows.DependencyProperty> Feld, definieren daher eine Abhängigkeitseigenschaft. Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel registriert eine Abhängigkeitseigenschaft zunächst durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> Methode. Der Name des Bezeichnerfelds, mit denen Sie den Namen zu speichern und Merkmale der Abhängigkeitseigenschaft muss die <xref:System.Windows.DependencyProperty.Name%2A> gewählten für die Abhängigkeitseigenschaft als Teil der <xref:System.Windows.DependencyProperty.Register%2A> Aufruf, der von der literalen Zeichenfolge angefügt `Property`. Z. B., wenn Sie eine Abhängigkeitseigenschaft mit dem Registrieren einer <xref:System.Windows.DependencyProperty.Name%2A> von `Location`, muss den Namen das ID-Feld, die Sie für die Abhängigkeitseigenschaft definieren `LocationProperty`.  
  
 In diesem Beispiel den Namen der Abhängigkeitseigenschaft und die zugehörige [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Accessor `State`; der Feld-ID ist `StateProperty`; der Typ der Eigenschaft ist <xref:System.Boolean>; und der Typ, der die Abhängigkeitseigenschaft registriert wird `MyStateControl`.  
  
 Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.  
  
 Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben. Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Weitere Informationen dazu, wie und warum eine Abhängigkeitseigenschaft implementiert wird, anstatt eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaft nur mit einem privaten Feld zu sichern, finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
