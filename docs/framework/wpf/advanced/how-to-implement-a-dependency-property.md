---
title: 'Gewusst wie: Implementieren einer Abhängigkeitseigenschaft'
description: Definieren Sie eine Abhängigkeits Eigenschaft in Windows Presentation Foundation, indem Sie eine Common Language Runtime Eigenschaft mit einem DependencyProperty-Feld unterstützen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165097"
---
# <a name="how-to-implement-a-dependency-property"></a>Gewusst wie: Implementieren einer Abhängigkeitseigenschaft
In diesem Beispiel wird gezeigt, wie Sie eine Common Language Runtime (CLR)-Eigenschaft mit einem <xref:System.Windows.DependencyProperty> Feld sichern und so eine Abhängigkeits Eigenschaft definieren. Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zuerst eine Abhängigkeits Eigenschaft durch Aufrufen der- <xref:System.Windows.DependencyProperty.Register%2A> Methode registriert. Der Name des Bezeichnerfelds, das Sie verwenden, um den Namen und die Merkmale der Abhängigkeits Eigenschaft zu speichern, muss das sein <xref:System.Windows.DependencyProperty.Name%2A> , das Sie für die Abhängigkeits Eigenschaft als Teil des <xref:System.Windows.DependencyProperty.Register%2A> Aufrufens ausgewählt haben `Property` . Wenn Sie beispielsweise eine Abhängigkeits Eigenschaft mit einem <xref:System.Windows.DependencyProperty.Name%2A> von registrieren `Location` , muss das Bezeichnerfeld, das Sie für die Abhängigkeits Eigenschaft definieren, benannt werden `LocationProperty` .  
  
 In diesem Beispiel ist der Name der Abhängigkeits Eigenschaft und der zugehörige CLR-Accessor `State` . Das Bezeichnerfeld ist, `StateProperty` der Typ der Eigenschaft ist, <xref:System.Boolean> und der Typ, der die Abhängigkeits Eigenschaft registriert, ist `MyStateControl` .  
  
 Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.  
  
 Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben. Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Weitere Informationen darüber, wie und warum eine Abhängigkeits Eigenschaft implementiert wird, anstatt nur eine CLR-Eigenschaft mit einem privaten Feld zu unterstützen, finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Artikel zu Vorgehensweisen](properties-how-to-topics.md)
