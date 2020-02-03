---
title: Binden von Steuerelementen an die BindingSource-Komponente mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744394"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="fbf51-102">Gewusst wie: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="fbf51-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="fbf51-103">Nachdem Sie dem Formular Steuerelemente hinzugefügt und die Benutzeroberfläche für die Anwendung bestimmt haben, können Sie die Steuerelemente an eine Datenquelle binden, sodass Benutzer zur Laufzeit Daten im Zusammenhang mit der Anwendung ändern und speichern können.</span><span class="sxs-lookup"><span data-stu-id="fbf51-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="fbf51-104">Das Binden eines Steuer Elements oder einer Reihe von Steuerelementen in Windows Forms wird am einfachsten mithilfe des <xref:System.Windows.Forms.BindingSource> Steuer Elements als Brücke zwischen den Steuerelementen auf dem Formular und der Datenquelle erreicht.</span><span class="sxs-lookup"><span data-stu-id="fbf51-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="fbf51-105">Mindestens ein Steuerelement in einem Formular kann an Daten gebunden werden. Im folgenden Verfahren wird ein <xref:System.Windows.Forms.TextBox>-Steuerelement an eine Datenquelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="fbf51-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="fbf51-106">Um das Verfahren abzuschließen, wird davon ausgegangen, dass Sie eine Bindung an eine Datenquelle herstellen, die von einer Datenbank abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="fbf51-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="fbf51-107">Weitere Informationen zum Erstellen von Datenquellen aus anderen Daten speichern finden Sie unter [Hinzufügen neuer Datenquellen](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="fbf51-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="fbf51-108">So binden Sie ein Steuerelement zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fbf51-108">To bind a control at design time</span></span>

1. <span data-ttu-id="fbf51-109">Ziehen Sie ein <xref:System.Windows.Forms.TextBox>-Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="fbf51-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="fbf51-110">Im **Eigenschaften** Fenster:</span><span class="sxs-lookup"><span data-stu-id="fbf51-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="fbf51-111">Erweitern Sie den Knoten **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="fbf51-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="fbf51-112">Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fbf51-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="fbf51-113">Der Benutzeroberflächen-Typ-Editor für die **Daten** Quelle wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fbf51-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="fbf51-114">Wenn eine Datenquelle bereits für das Projekt oder Formular konfiguriert wurde, wird Sie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbf51-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="fbf51-115">Klicken Sie auf **Projektdatenquelle hinzufügen**, um die Daten zu verbinden und die Datenquelle zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="fbf51-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="fbf51-116">Klicken Sie auf der Startseite des **Assistenten zum Konfigurieren von Datenquellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fbf51-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="fbf51-117">Wählen Sie auf der Seite **Daten Quellentyp auswählen** die Option **Datenbank**aus.</span><span class="sxs-lookup"><span data-stu-id="fbf51-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="fbf51-118">Wählen Sie auf der Seite **Wählen Sie Ihre Datenverbindung** aus eine Datenverbindung aus der Liste der verfügbaren Verbindungen aus.</span><span class="sxs-lookup"><span data-stu-id="fbf51-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="fbf51-119">Wenn die gewünschte Datenverbindung nicht verfügbar ist, wählen Sie **neue Verbindung** aus, um eine neue Datenverbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbf51-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="fbf51-120">Wählen Sie **Ja, Verbindung speichern,** um die Verbindungs Zeichenfolge in der Anwendungs Konfigurationsdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fbf51-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="fbf51-121">Wählen Sie die Datenbankobjekte, die in die Anwendung gebracht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fbf51-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="fbf51-122">Wählen Sie in diesem Fall ein Feld in einer Tabelle aus, das <xref:System.Windows.Forms.TextBox> Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="fbf51-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="fbf51-123">Ersetzen Sie den Standardnamen des Datasets falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="fbf51-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="fbf51-124">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="fbf51-124">Click **Finish**.</span></span>

11. <span data-ttu-id="fbf51-125">Klicken Sie im **Eigenschaften** Fenster erneut auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fbf51-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="fbf51-126">Wählen Sie im **Datenquellen** -Editor für die Datenquelle den Namen des Felds aus, an das die <xref:System.Windows.Forms.TextBox> gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="fbf51-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="fbf51-127">Der Editor für die Benutzeroberflächen Typen der Datenquelle wird geschlossen, und das **DataSet** , der <xref:System.Windows.Forms.BindingSource> und der Tabellen Adapter für diese Datenverbindung werden dem Formular hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fbf51-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf51-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbf51-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="fbf51-129">Neue Datenquelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="fbf51-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="fbf51-130">[Datenquellen Fenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="fbf51-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
