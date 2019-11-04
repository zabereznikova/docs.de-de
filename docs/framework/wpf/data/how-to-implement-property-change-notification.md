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
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="826ef-102">Gewusst wie: Implementieren von Benachrichtigungen bei Eigenschaftenänderungen</span><span class="sxs-lookup"><span data-stu-id="826ef-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="826ef-103">Um <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Bindung zu unterstützen, damit die Bindungs Zieleigenschaften die dynamischen Änderungen der Bindungs Quelle automatisch widerspiegeln (z. b. wenn der Vorschaubereich automatisch aktualisiert werden soll, wenn der Benutzer ein Formular bearbeitet), muss Ihre Klasse Geben Sie die richtigen Benachrichtigungen für die geänderte Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="826ef-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="826ef-104">Dieses Beispiel zeigt, wie eine Klasse erstellt wird, die <xref:System.ComponentModel.INotifyPropertyChanged>implementiert.</span><span class="sxs-lookup"><span data-stu-id="826ef-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="826ef-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="826ef-105">Example</span></span>  
 <span data-ttu-id="826ef-106">Um <xref:System.ComponentModel.INotifyPropertyChanged> zu implementieren, müssen Sie das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>-Ereignis deklarieren und die `OnPropertyChanged`-Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="826ef-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="826ef-107">Dann rufen Sie für jede Eigenschaft, für die Sie Änderungsbenachrichtigungen erhalten möchten, `OnPropertyChanged` auf, wenn die Eigenschaft aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="826ef-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="826ef-108">Ein Beispiel für die Verwendung der `Person`-Klasse zur Unterstützung <xref:System.Windows.Data.BindingMode.TwoWay> Bindung finden Sie unter [Steuern, wann der TextBox-Text die Quelle aktualisiert](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="826ef-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826ef-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="826ef-109">See also</span></span>

- [<span data-ttu-id="826ef-110">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="826ef-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="826ef-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="826ef-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="826ef-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="826ef-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
