---
title: 'Vorgehensweise: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: d37d468acc94470be8c2afdc495b40168932ec83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931442"
---
# <a name="how-to-implement-property-change-notification"></a>Vorgehensweise: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen
Zur Unterstützung <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Binden an die bindungszieleigenschaften automatisch entsprechend der dynamischen Änderungen der Bindungsquelle (z. B. der Vorschaubereich automatisch aktualisiert, wenn der Benutzer ein Formular bearbeitet haben), aktivieren Sie die Klasse Benachrichtigungen bei der richtigen eigenschaftenänderungen bereitstellen muss. Dieses Beispiel zeigt, wie Sie eine Klasse erstellen, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Beispiel  
 Zum Implementieren <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie deklarieren die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis, und erstellen Sie die `OnPropertyChanged` Methode. Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Finden Sie ein Beispiel dafür, wie die `Person` Klasse kann verwendet werden, um die Unterstützung von <xref:System.Windows.Data.BindingMode.TwoWay> Bindung, finden Sie unter [steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
