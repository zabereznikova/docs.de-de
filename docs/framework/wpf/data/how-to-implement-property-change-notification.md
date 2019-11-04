---
title: 'Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen'
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
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459745"
---
# <a name="how-to-implement-property-change-notification"></a>Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen
Um <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Bindung zu unterstützen, damit die Bindungs Zieleigenschaften die dynamischen Änderungen der Bindungs Quelle automatisch widerspiegeln (z. b. wenn der Vorschaubereich automatisch aktualisiert werden soll, wenn der Benutzer ein Formular bearbeitet), muss Ihre Klasse Geben Sie die richtigen Benachrichtigungen für die geänderte Eigenschaft an. Dieses Beispiel zeigt, wie eine Klasse erstellt wird, die <xref:System.ComponentModel.INotifyPropertyChanged>implementiert.  
  
## <a name="example"></a>Beispiel  
 Um <xref:System.ComponentModel.INotifyPropertyChanged> zu implementieren, müssen Sie das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>-Ereignis deklarieren und die `OnPropertyChanged`-Methode erstellen. Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Ein Beispiel für die Verwendung der `Person`-Klasse zur Unterstützung <xref:System.Windows.Data.BindingMode.TwoWay> Bindung finden Sie unter [Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
