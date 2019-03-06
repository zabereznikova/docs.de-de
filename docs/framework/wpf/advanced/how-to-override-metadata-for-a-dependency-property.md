---
title: 'Vorgehensweise: Überschreiben von Metadaten für eine Abhängigkeitseigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
ms.openlocfilehash: 5d2d692984bef34569b2c4bb80c3fb072e4c3f79
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365879"
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a>Vorgehensweise: Überschreiben von Metadaten für eine Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie Sie die standardmäßigen Metadaten von Abhängigkeitseigenschaften überschreiben, die durch den Aufruf einer geerbten Klasse stammen die <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> -Methode und typspezifische Metadaten bereitgestellt.  
  
## <a name="example"></a>Beispiel  
 Durch die Definition der <xref:System.Windows.PropertyMetadata>, eine Klasse kann der Abhängigkeitseigenschaft-Verhalten, wie die Standard-Wert und systemrückrufe definieren. Viele Abhängigkeitseigenschaftenklassen verfügen bereits über Standardmetadaten als Teil ihres Registrierungsprozesses. Hierzu gehören die Abhängigkeitseigenschaften der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]. Eine Klasse, die die Abhängigkeitseigenschaft über ihre Klassenvererbung erbt, kann die ursprünglichen Metadaten überschreiben, sodass die Merkmale der Eigenschaft, die über Metadaten geändert werden können, allen unterklassenspezifischen Anforderungen entsprechen.  
  
 Das Überschreiben von Metadaten für eine Abhängigkeitseigenschaft muss vor der Verwendung dieser Eigenschaft durchgeführt werden (dies entspricht der Zeit, in der bestimmte Instanzen von Objekten, die die Eigenschaft registrieren, instanziiert werden). Aufrufe von <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> muss ausgeführt werden, in den statischen Konstruktoren des Typs, der sich selbst als die `forType` Parameter <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Wenn Sie versuchen, die Metadaten zu ändern, nachdem Instanzen des Besitzertyps vorhanden sind, werden zwar keine Ausnahmen ausgelöst, jedoch inkonsistentes Verhalten im Eigenschaftensystem hervorgerufen. Außerdem können Metadaten nur einmal pro Typ überschrieben werden. Bei nachfolgenden Versuchen, Metadaten für den gleichen Typ zu überschreiben, wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel überschreibt die benutzerdefinierte Klasse `MyAdvancedStateControl` die von `MyAdvancedStateControl` für `StateProperty` bereitgestellten Metadaten mit neuen Eigenschaftenmetadaten. Bei der Abfrage der Eigenschaft für eine neu erstellte `MyAdvancedStateControl`-Instanz, lautet der Standardwert von `StateProperty` nun `true`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Themen zu Vorgehensweisen](properties-how-to-topics.md)
