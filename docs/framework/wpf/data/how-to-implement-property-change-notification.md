---
title: 'Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen'
description: Aktivieren Sie Ihre Eigenschaften, um eine Bindungs Quelle automatisch zu benachrichtigen, wenn sich der Eigenschafts Wert in Windows Presentation Foundation (WPF) ändert.
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
ms.openlocfilehash: 6c298930b7b1f812e94ea6add8f53c67d3453530
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620780"
---
# <a name="how-to-implement-property-change-notification"></a>Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen
Um die <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> dynamischen Änderungen der Bindungs Quelle automatisch widerzuspiegeln (z. b. wenn der Vorschaubereich automatisch aktualisiert werden soll, wenn der Benutzer ein Formular bearbeitet), muss die Klasse die richtigen Benachrichtigungen über geänderte Eigenschaften bereitstellen, damit die Bindungs Zieleigenschaften die dynamischen Änderungen der Bindungs Quelle automatisch widerspiegeln. Dieses Beispiel zeigt, wie eine Klasse erstellt wird, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged> .  
  
## <a name="example"></a>Beispiel  
 Zum Implementieren von <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> -Ereignis deklarieren und die-Methode erstellen `OnPropertyChanged` . Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Ein Beispiel für die Verwendung der- `Person` Klasse zur Unterstützung von Bindungen finden Sie unter <xref:System.Windows.Data.BindingMode.TwoWay> [Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
