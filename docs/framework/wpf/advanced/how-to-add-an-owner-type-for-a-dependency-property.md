---
title: 'Vorgehensweise: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 528ec28750c6ce7dffb1104d750679a546df0487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697061"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Vorgehensweise: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie Sie eine Klasse hinzugefügt werden, als Besitzer einer Abhängigkeitseigenschaft, die für einen anderen Typ registriert. Auf diese Weise die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader und Eigenschaftensystem sind beide erkennen, die Klasse als weiteren Besitzer der Eigenschaft. Optional als Besitzer hinzufügen, können die hinzufügende Klasse um typspezifische Metadaten bereitzustellen.  
  
 Im folgenden Beispiel `StateProperty` wird durch eine Eigenschaft registriert die `MyStateControl` Klasse. Die Klasse `UnrelatedStateControl` fügt sich selbst als Besitzer der `StateProperty` mithilfe der <xref:System.Windows.DependencyProperty.AddOwner%2A> Methode, die speziell mit der Signatur, die neue Metadaten für die Abhängigkeitseigenschaft ermöglicht, wie sie auf der hinzufügen-Typ vorhanden ist. Beachten Sie, den Sie bereitstellen sollten [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Accessoren für die Eigenschaft ähnelt dem Beispiel in der [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) , sowie die Bezeichner der Abhängigkeitseigenschaft in der Klasse hinzugefügt wird, erneut verfügbar machen als Besitzer.  
  
 Ohne Wrapper die Abhängigkeitseigenschaft funktioniert trotzdem aus der Perspektive des programmgesteuerten Zugriffs mit <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>. Aber Sie möchten in der Regel parallel dieses Eigenschaftensystem Verhalten mit der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaftenwrapper. Die Wrapper erleichtern es, die die Abhängigkeitseigenschaft programmgesteuert festgelegt und ermöglichen das Festlegen der Eigenschaften als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute.  
  
 Um herauszufinden, wie die standardmäßigen Metadaten überschrieben, finden Sie unter [Überschreiben von Metadaten für eine Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
