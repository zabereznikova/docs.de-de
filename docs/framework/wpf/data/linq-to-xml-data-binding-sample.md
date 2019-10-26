---
title: Beispiel für LINQ to XML Datenbindung
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921221"
---
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="e86e5-102">Beispiel für LINQ to XML Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e86e5-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="e86e5-103">In diesem Artikel wird das LinqToXmlDataBinding-Beispiel beschrieben, eine Windows Presentation Foundation-app (WPF), die Benutzeroberflächen Komponenten an eine eingebettete XML-Datenquelle bindet.</span><span class="sxs-lookup"><span data-stu-id="e86e5-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="e86e5-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e86e5-104">Overview</span></span>

<span data-ttu-id="e86e5-105">Das LinqToXmlDataBinding-Beispiel ist eine Windows Presentation Foundation-app (WPF) C# , die-und XAML-Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="e86e5-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="e86e5-106">Ein eingebettetes XML-Dokument definiert eine Liste von Büchern.</span><span class="sxs-lookup"><span data-stu-id="e86e5-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="e86e5-107">Die APP ermöglicht dem Benutzer, die Buch Einträge anzuzeigen, hinzuzufügen, zu löschen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e86e5-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="e86e5-108">Es gibt zwei primäre Quelldateien:</span><span class="sxs-lookup"><span data-stu-id="e86e5-108">There are two primary source files:</span></span>

- <span data-ttu-id="e86e5-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) enthält den XAML-Deklarationscode für die Benutzeroberfläche des Hauptfensters.</span><span class="sxs-lookup"><span data-stu-id="e86e5-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="e86e5-110">Sie enthält außerdem einen Abschnitt mit einer Fenster Ressource, in dem ein Datenanbieter und ein eingebettetes XML-Dokument für die Buch Listen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e86e5-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="e86e5-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) enthält die Initialisierungs- und Ereignisbehandlungsmethoden, die der Benutzeroberfläche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e86e5-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="e86e5-112">Das Hauptfenster ist in die folgenden vier vertikalen Benutzeroberflächenabschnitte unterteilt:</span><span class="sxs-lookup"><span data-stu-id="e86e5-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="e86e5-113">**XML**: Zeigt die unformatierte XML-Quelle der eingebetteten Bücherliste an.</span><span class="sxs-lookup"><span data-stu-id="e86e5-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="e86e5-114">**Book List** (Bücherliste): Zeigt die Bucheinträge als Standardtext an, und versetzt den Benutzer in die Lage, einzelne Einträge auszuwählen und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e86e5-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="e86e5-115">**Edit Selected Book** (Ausgewähltes Buch bearbeiten): Ermöglicht es dem Benutzer, die dem aktuell ausgewählten Bucheintrag zugeordneten Werte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e86e5-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="e86e5-116">**Add New Book** (Neues Buch hinzufügen): Ermöglicht das Erstellen eines neuen Bucheintrags anhand der vom Benutzer eingegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="e86e5-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="e86e5-117">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="e86e5-117">Run the sample</span></span>

<span data-ttu-id="e86e5-118">In diesem Abschnitt wird gezeigt, wie Sie das LinqToXmlDataBinding-Projekt in Visual Studio erstellen und erstellen und wie Sie die resultierende LinqToXmlDataBinding-Windows Presentation Foundation (WPF)-app ausführen.</span><span class="sxs-lookup"><span data-stu-id="e86e5-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="e86e5-119">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="e86e5-119">Create the project</span></span>

1. <span data-ttu-id="e86e5-120">Starten Sie Visual Studio, und erstellen Sie eine C#-**WPF-App** mit dem Namen **LinqToXmlDataBinding**.</span><span class="sxs-lookup"><span data-stu-id="e86e5-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="e86e5-121">Das Projekt muss .NET Framework 3.5 (oder höher) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e86e5-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="e86e5-122">Sofern nicht bereits vorhanden, fügen Sie Projektverweise für die folgenden .NET-Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="e86e5-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="e86e5-123"><legacyBold>System.Data</legacyBold></span><span class="sxs-lookup"><span data-stu-id="e86e5-123">System.Data</span></span>
    - <span data-ttu-id="e86e5-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="e86e5-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="e86e5-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="e86e5-125">System.Xml</span></span>
    - <span data-ttu-id="e86e5-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="e86e5-126">System.Xml</span></span>

1. <span data-ttu-id="e86e5-127">Erstellen Sie die Projektmappe, indem Sie **STRG**+**UMSCHALTTASTE**+**B** drücken, und führen Sie sie dann mit **F5** aus.</span><span class="sxs-lookup"><span data-stu-id="e86e5-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="e86e5-128">Das Projekt sollte ohne Fehler kompiliert und als generische WPF-Anwendung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e86e5-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="e86e5-129">Code hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e86e5-129">Add code</span></span>

1. <span data-ttu-id="e86e5-130">Benennen Sie im **Projektmappen-Explorer** die Quelldatei **Window1.xaml** in **L2XDBForm.xaml** um.</span><span class="sxs-lookup"><span data-stu-id="e86e5-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="e86e5-131">Die abhängige Quelldatei Window1.XAML.cs wird automatisch in L2XDBForm.XAML.cs umbenannt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="e86e5-132">Ersetzen Sie den Quellcode in der Datei **L2XDBForm. XAML** durch den [Quellcode L2DBForm. XAML](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="e86e5-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="e86e5-133">Verwenden Sie zum Arbeiten mit dieser Datei die XAML-Quellansicht.</span><span class="sxs-lookup"><span data-stu-id="e86e5-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="e86e5-134">Ersetzen Sie auch die Quelle in **L2XDBForm.XAML.cs** durch den [L2DBForm.XAML.cs-Quellcode](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="e86e5-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="e86e5-135">Ersetzen Sie in der Datei **app. XAML**alle Vorkommen der Zeichenfolge **Window1. XAML** durch **L2XDBForm. XAML**.</span><span class="sxs-lookup"><span data-stu-id="e86e5-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="e86e5-136">Erstellen Sie die Projektmappe, indem Sie **STRG**+**UMSCHALTTASTE**+**B** drücken.</span><span class="sxs-lookup"><span data-stu-id="e86e5-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="e86e5-137">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="e86e5-137">Run the app</span></span>

<span data-ttu-id="e86e5-138">Die LinqToXmlDataBinding-App ermöglicht dem Benutzer, eine Liste von Büchern anzuzeigen und zu bearbeiten, die als eingebettetes XML-Element gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e86e5-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="e86e5-139">Führen Sie die APP aus, indem Sie **F5** drücken (Debuggen starten) oder **STRG**+**F5** (Starten ohne Debugging).</span><span class="sxs-lookup"><span data-stu-id="e86e5-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="e86e5-140">Daraufhin wird ein Programmfenster mit dem Titel **WPF-Datenbindung mit LINQ to XML** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="e86e5-141">Im obersten Abschnitt der Benutzeroberfläche wird das unformatierte **XML** angezeigt, das die Buchliste darstellt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="e86e5-142">Die Anzeige erfolgt unter Verwendung eines WPF-<xref:System.Windows.Controls.TextBlock>-Steuerelements, das keine Interaktion mithilfe von Maus oder Tastatur zulässt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="e86e5-143">Im zweiten vertikalen Abschnitt mit der Bezeichnung **Book List** (Buchliste) werden die Bücher als geordnete Nur-Text-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="e86e5-144">Dazu wird ein <xref:System.Windows.Controls.ListBox>-Steuerelement verwendet, das die Auswahl über Maus oder Tastatur zulässt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="e86e5-145">Bücher hinzufügen und löschen</span><span class="sxs-lookup"><span data-stu-id="e86e5-145">Add and delete books</span></span>

<span data-ttu-id="e86e5-146">Wenn Sie der Liste ein neues Buch hinzufügen möchten, geben Sie im Abschnitt **ID** und **Wert** <xref:System.Windows.Controls.TextBox>-Steuerelemente im letzten Abschnitt, **Add New Book**, Werte ein, und wählen Sie dann **Book hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e86e5-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="e86e5-147">Das Buch wird in der Liste der Buch-und XML-Auflistungen an die Liste angefügt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="e86e5-148">Das Programm prüft die Eingabewerte nicht auf ihre Gültigkeit.</span><span class="sxs-lookup"><span data-stu-id="e86e5-148">This program does not validate input values.</span></span>

<span data-ttu-id="e86e5-149">Wenn Sie ein vorhandenes Buch aus der Liste löschen möchten, wählen Sie es im Abschnitt **Book List** aus, und wählen Sie dann **Ausgewähltes Buch entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="e86e5-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="e86e5-150">Der Bucheintrag wird aus dem Buch und den unformatierten XML-Quell Auflistungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="e86e5-151">Bucheintrag bearbeiten</span><span class="sxs-lookup"><span data-stu-id="e86e5-151">Edit a book entry</span></span>

1. <span data-ttu-id="e86e5-152">Wählen Sie den Bucheintrag im zweiten Abschnitt, **Book List**, aus.</span><span class="sxs-lookup"><span data-stu-id="e86e5-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="e86e5-153">Die aktuellen Werte werden im Abschnitt **Edit Selected Book** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e86e5-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="e86e5-154">Bearbeiten Sie die Werte mit der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="e86e5-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="e86e5-155">Sobald das <xref:System.Windows.Controls.TextBox>-Steuerelement den Fokus verliert, werden Änderungen automatisch an die XML-Quell-und-Buch Auflistungen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="e86e5-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
