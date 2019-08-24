---
title: 'Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einer Windows Forms-Instanz'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: df87f00e6e03de67c3fb1adc28472c96f4a47ef4
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015629"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="759bd-102">Vorgehensweise: Erstellen eines einfach gebundenen Steuer Elements in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="759bd-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="759bd-103">Mit der *einfachen Bindung*können Sie in einem-Steuerelement ein einzelnes Datenelement, z. b. einen Spaltenwert aus einer Datasettabelle, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="759bd-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="759bd-104">Sie können eine beliebige Eigenschaft eines Steuer Elements an einen Datenwert binden.</span><span class="sxs-lookup"><span data-stu-id="759bd-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="759bd-105">So binden Sie ein Steuerelement einfach</span><span class="sxs-lookup"><span data-stu-id="759bd-105">To simple-bind a control</span></span>

1. <span data-ttu-id="759bd-106">Stellen Sie die Verbindung zu einer Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="759bd-106">Connect to a data source.</span></span> <span data-ttu-id="759bd-107">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="759bd-107">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="759bd-108">Wählen Sie in Visual Studio das Steuerelement auf dem Formular aus, und zeigen Sie das **Eigenschaften** Fenster an.</span><span class="sxs-lookup"><span data-stu-id="759bd-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="759bd-109">Erweitern Sie die Eigenschaft **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="759bd-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="759bd-110">Die Eigenschaften, die am häufigsten gebunden werden, werden unterhalb der **(DataBindings)** -Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="759bd-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="759bd-111">In den meisten Steuerelementen ist die **Text** -Eigenschaft z. b. am häufigsten gebunden.</span><span class="sxs-lookup"><span data-stu-id="759bd-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="759bd-112">Wenn die Eigenschaft, die Sie binden möchten, nicht eine der häufig gebundenen Eigenschaften ist, klicken Sie auf die Schalt![Fläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png).) im Feld **(erweitert)** , um das  **Dialogfeld "Formatierung und erweiterte Bindung** " mit einer kompletten Liste der Eigenschaften für dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="759bd-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="759bd-113">Wählen Sie die Eigenschaft aus, die Sie binden möchten, und klicken Sie auf den Dropdown Pfeil unter **Bindung**.</span><span class="sxs-lookup"><span data-stu-id="759bd-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="759bd-114">Nun wird eine Liste verfügbarer Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="759bd-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="759bd-115">Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.</span><span class="sxs-lookup"><span data-stu-id="759bd-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="759bd-116">Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="759bd-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="759bd-117">Klicken Sie auf den Namen des Elements, das gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="759bd-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="759bd-118">Wenn Sie im Dialogfeld **Formatierung und erweiterte Bindung** gearbeitet haben, klicken Sie auf **OK** , um zum **Eigenschaften** Fenster zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="759bd-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="759bd-119">Wenn Sie zusätzliche Eigenschaften für das Steuerelement binden möchten, wiederholen Sie die Schritte 3 bis 7.</span><span class="sxs-lookup"><span data-stu-id="759bd-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="759bd-120">Da einfach gebundene Steuerelemente nur ein einzelnes Datenelement anzeigen, ist es sehr typisch, Navigations Logik in ein Windows Form-Steuerelement mit einfachen gebundenen Steuerelementen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="759bd-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="759bd-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="759bd-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="759bd-122">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="759bd-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="759bd-123">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="759bd-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
