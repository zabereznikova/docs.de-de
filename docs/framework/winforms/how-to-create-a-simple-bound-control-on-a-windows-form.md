---
title: 'Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: ce4585a1c5c2b9acbdb7ec33c62a1e91851b720e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538817"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="24373-102">Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="24373-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="24373-103">Mit *einfache Bindung*, können Sie ein einzelnes Datenelement, z. B. einen Spaltenwert in einer Dataset-Tabelle in einem Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24373-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="24373-104">Sie können einfache-eine Eigenschaft eines Steuerelements an einen Datenwert binden.</span><span class="sxs-lookup"><span data-stu-id="24373-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24373-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="24373-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="24373-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="24373-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="24373-107">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="24373-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="24373-108">Simple-eines Steuerelements binden.</span><span class="sxs-lookup"><span data-stu-id="24373-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="24373-109">Stellen Sie die Verbindung zu einer Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="24373-109">Connect to a data source.</span></span> <span data-ttu-id="24373-110">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="24373-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="24373-111">Klicken Sie im Formular, wählen Sie das Steuerelement, und Anzeigen der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="24373-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="24373-112">Erweitern Sie die **(DataBindings)** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24373-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="24373-113">Die Eigenschaften, die am häufigsten gebunden werden angezeigt, darunter die **(DataBindings)** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24373-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="24373-114">Beispielsweise ist in den meisten Steuerelementen die **Text** am häufigsten Eigenschaft gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="24373-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="24373-115">Die Eigenschaft Sie nach Bedarf Bindung ist nicht der häufig gebundenen Eigenschaften, klicken Sie auf die **Auslassungszeichen** Schaltfläche (![von VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton") ) in der **(Erweitert)** Feld zum Anzeigen der **Formatierung und erweiterte Bindung** Dialogfeld mit einer vollständigen Liste der Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="24373-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="24373-116">Wählen Sie die Eigenschaft zu binden, und klicken Sie auf den Dropdownpfeil unter **binden**.</span><span class="sxs-lookup"><span data-stu-id="24373-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="24373-117">Nun wird eine Liste verfügbarer Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24373-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="24373-118">Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.</span><span class="sxs-lookup"><span data-stu-id="24373-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="24373-119">Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24373-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="24373-120">Klicken Sie auf den Namen des Elements, das gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="24373-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="24373-121">Wenn Sie, in bearbeitet haben der **Formatierung und erweiterte Bindung** (Dialogfeld), klicken Sie auf **OK** wieder die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="24373-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="24373-122">Wenn Sie zusätzliche Eigenschaften für das Steuerelement binden möchten, wiederholen Sie Schritte 3 bis 7.</span><span class="sxs-lookup"><span data-stu-id="24373-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24373-123">Da einfach gebundene Steuerelemente nur ein einzelnes Datenelement anzuzeigen, ist es sehr typisch Navigationslogik in einem Windows Form mit einfach gebundenen Steuerelementen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24373-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24373-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24373-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="24373-125">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="24373-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="24373-126">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24373-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
