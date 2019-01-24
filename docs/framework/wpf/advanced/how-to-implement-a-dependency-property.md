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
ms.openlocfilehash: 90eb15d3cc0d9a6c1d07879b0166da4d45d786be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727325"
---
# <a name="how-to-implement-a-dependency-property"></a>Vorgehensweise: Implementieren einer Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie Sie eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Eigenschaft mit einer <xref:System.Windows.DependencyProperty> Feld so eine Abhängigkeitseigenschaft definieren. Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zuerst registriert eine Abhängigkeitseigenschaft durch Aufrufen der <xref:System.Windows.DependencyProperty.Register%2A> Methode. Der Name des Bezeichnerfelds, die Sie verwenden, um den Namen zu speichern und die Merkmale der Abhängigkeitseigenschaft muss die <xref:System.Windows.DependencyProperty.Name%2A> gewählten für die Abhängigkeitseigenschaft als Teil der <xref:System.Windows.DependencyProperty.Register%2A> -Aufrufs der literalen Zeichenfolge `Property`. Z. B. Wenn Sie eine Abhängigkeitseigenschaft mit Registrieren einer <xref:System.Windows.DependencyProperty.Name%2A> von `Location`, und klicken Sie dann das Feld "ID", die Sie für die Abhängigkeitseigenschaft definieren genannt werden muss `LocationProperty`.  
  
 In diesem Beispiel ist der Name der Abhängigkeitseigenschaft und dessen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Accessor `State`; das Bezeichnerfeld ist `StateProperty`; der Typ der Eigenschaft ist <xref:System.Boolean>; und der Typ, der die Abhängigkeitseigenschaft registriert `MyStateControl`.  
  
 Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.  
  
 Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben. Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Weitere Informationen dazu, wie und warum eine Abhängigkeitseigenschaft implementiert wird, anstatt eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaft nur mit einem privaten Feld zu sichern, finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
