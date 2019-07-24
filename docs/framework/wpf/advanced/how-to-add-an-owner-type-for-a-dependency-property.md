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
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401132"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Vorgehensweise: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie eine Klasse als Besitzer einer Abhängigkeits Eigenschaft hinzugefügt wird, die für einen anderen Typ registriert ist. Auf diese Weise können sowohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader als auch das Eigenschaften System die Klasse als zusätzlichen Besitzer der Eigenschaft erkennen. Durch das Hinzufügen als Besitzer kann die hinzu fügende Klasse optional typspezifische Metadaten bereitstellen.  
  
 Im folgenden Beispiel ist eine `StateProperty` Eigenschaft, die von der `MyStateControl` -Klasse registriert wird. Die- `UnrelatedStateControl` Klasse fügt sich selbst als Besitzer `StateProperty` der mithilfe der <xref:System.Windows.DependencyProperty.AddOwner%2A> -Methode hinzu, insbesondere mithilfe der Signatur, die neue Metadaten für die Abhängigkeits Eigenschaft zulässt, wie Sie im hinzugefügten Typ vorhanden ist. Beachten Sie, dass Sie Common Language Runtime (CLR)-Accessoren für die-Eigenschaft bereitstellen sollten, ähnlich wie im Beispiel im Beispiel [Implementieren einer Abhängigkeits Eigenschaft](how-to-implement-a-dependency-property.md) , und machen Sie den Bezeichner der Abhängigkeits Eigenschaft für die Klasse, die als Besitzer hinzugefügt wird, erneut verfügbar.  
  
 Ohne Wrapper funktioniert die Abhängigkeits Eigenschaft immer noch aus der Perspektive des programmgesteuerten Zugriffs mithilfe <xref:System.Windows.DependencyObject.GetValue%2A> von <xref:System.Windows.DependencyObject.SetValue%2A>oder. Allerdings möchten Sie dieses Eigenschaften Systemverhalten in der Regel mit den CLR-Eigenschaftenwrappern parallel durchlaufen. Die Wrapper vereinfachen die programmgesteuerte Festlegung der Abhängigkeits Eigenschaft und ermöglichen das Festlegen der Eigenschaften als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute.  
  
 Weitere Informationen zum Überschreiben von Standard Metadaten finden Sie unter [Überschreiben von Metadaten für eine Abhängigkeits Eigenschaft](how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
