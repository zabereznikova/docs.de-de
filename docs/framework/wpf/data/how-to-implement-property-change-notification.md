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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204353"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="73b59-102">Vorgehensweise: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen</span><span class="sxs-lookup"><span data-stu-id="73b59-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="73b59-103">Zur Unterstützung <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Binden an die bindungszieleigenschaften automatisch entsprechend der dynamischen Änderungen der Bindungsquelle (z. B. der Vorschaubereich automatisch aktualisiert, wenn der Benutzer ein Formular bearbeitet haben), aktivieren Sie die Klasse Benachrichtigungen bei der richtigen eigenschaftenänderungen bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="73b59-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="73b59-104">Dieses Beispiel zeigt, wie Sie eine Klasse erstellen, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="73b59-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b59-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73b59-105">Example</span></span>  
 <span data-ttu-id="73b59-106">Zum Implementieren <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie deklarieren die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis, und erstellen Sie die `OnPropertyChanged` Methode.</span><span class="sxs-lookup"><span data-stu-id="73b59-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="73b59-107">Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="73b59-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="73b59-108">Finden Sie ein Beispiel dafür, wie die `Person` Klasse kann verwendet werden, um die Unterstützung von <xref:System.Windows.Data.BindingMode.TwoWay> Bindung, finden Sie unter [steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="73b59-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b59-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73b59-109">See also</span></span>

- [<span data-ttu-id="73b59-110">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="73b59-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="73b59-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="73b59-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="73b59-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="73b59-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
