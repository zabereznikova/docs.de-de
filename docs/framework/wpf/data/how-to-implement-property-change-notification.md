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
ms.openlocfilehash: 7a8ab232019f1266095091cd4e1ce6e7fec63207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587808"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="5c790-102">Vorgehensweise: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen</span><span class="sxs-lookup"><span data-stu-id="5c790-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="5c790-103">Zur Unterstützung <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Binden an die bindungszieleigenschaften automatisch entsprechend der dynamischen Änderungen der Bindungsquelle (z. B. der Vorschaubereich automatisch aktualisiert, wenn der Benutzer ein Formular bearbeitet haben), aktivieren Sie die Klasse Benachrichtigungen bei der richtigen eigenschaftenänderungen bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="5c790-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="5c790-104">Dieses Beispiel zeigt, wie Sie eine Klasse erstellen, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="5c790-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c790-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c790-105">Example</span></span>  
 <span data-ttu-id="5c790-106">Zum Implementieren <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie deklarieren die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis, und erstellen Sie die `OnPropertyChanged` Methode.</span><span class="sxs-lookup"><span data-stu-id="5c790-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="5c790-107">Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5c790-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="5c790-108">Finden Sie ein Beispiel dafür, wie die `Person` Klasse kann verwendet werden, um die Unterstützung von <xref:System.Windows.Data.BindingMode.TwoWay> Bindung, finden Sie unter [steuern, wann der TextBox-Text die Quelle aktualisiert](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="5c790-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c790-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c790-109">See also</span></span>
- [<span data-ttu-id="5c790-110">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="5c790-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)
- [<span data-ttu-id="5c790-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="5c790-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5c790-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5c790-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
