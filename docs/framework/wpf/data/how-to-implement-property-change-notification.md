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
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555989"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="d525a-102">Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen</span><span class="sxs-lookup"><span data-stu-id="d525a-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="d525a-103">Zur Unterstützung <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Binden an die Ziel-Bindungseigenschaften automatisch entsprechend der dynamischen Änderungen der Bindungsquelle (z. B. im Vorschaufenster automatisch aktualisiert, wenn der Benutzer ein Formulars bearbeitet haben), aktivieren eine Klasse muss die richtige geänderten Eigenschaft Benachrichtigungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d525a-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="d525a-104">In diesem Beispiel wird gezeigt, wie eine Klasse erstellen, die implementiert <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="d525a-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d525a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d525a-105">Example</span></span>  
 <span data-ttu-id="d525a-106">Implementiert <xref:System.ComponentModel.INotifyPropertyChanged> müssen Sie deklarieren die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis, und erstellen Sie die `OnPropertyChanged` Methode.</span><span class="sxs-lookup"><span data-stu-id="d525a-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="d525a-107">Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d525a-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="d525a-108">Ein Beispiel gezeigt, wie die `Person` Klasse kann verwendet werden, um Unterstützung <xref:System.Windows.Data.BindingMode.TwoWay> binden, finden Sie unter [steuern, wann der TextBox-Text die Quelle aktualisiert](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="d525a-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d525a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d525a-109">See Also</span></span>  
 [<span data-ttu-id="d525a-110">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="d525a-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="d525a-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d525a-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="d525a-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d525a-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
