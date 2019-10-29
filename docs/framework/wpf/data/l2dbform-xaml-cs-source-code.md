---
title: L2DBForm.xaml.cs-Quellcode
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921155"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="90e2d-102">L2DBForm.xaml.cs-Quellcode</span><span class="sxs-lookup"><span data-stu-id="90e2d-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="90e2d-103">Diese Seite enthält den Inhalt und die Beschreibung des C# Quellcodes in der Datei *L2DBForm.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="90e2d-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="90e2d-104">Die in dieser Datei enthaltene L2XDBForm-Teilklasse kann in die folgenden drei logischen Abschnitte unterteilt werden: Datenmember und die Ereignishandler `OnRemove` und `OnAddBook` für das Klicken auf Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="90e2d-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="90e2d-105">Datenmember</span><span class="sxs-lookup"><span data-stu-id="90e2d-105">Data members</span></span>

<span data-ttu-id="90e2d-106">Für die Zuordnung dieser Klasse zu den in *L2DBForm.xaml* verwendeten Fensterressourcen werden zwei private Datenmember verwendet.</span><span class="sxs-lookup"><span data-stu-id="90e2d-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="90e2d-107">Die `myBooks`-Namespacevariable wird mit `"http://www.mybooks.com"` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="90e2d-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="90e2d-108">Der `bookList`-Member wird im Konstruktor mit der folgenden Zeile in die CDATA-Zeichenfolge in *L2DBForm.xaml* initialisiert:</span><span class="sxs-lookup"><span data-stu-id="90e2d-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="90e2d-109">Ereignishandler „OnAddBook“</span><span class="sxs-lookup"><span data-stu-id="90e2d-109">OnAddBook event handler</span></span>

<span data-ttu-id="90e2d-110">Diese Methode enthält die folgenden drei Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="90e2d-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="90e2d-111">Die erste Bedingungsanweisung wird zur Eingabevalidierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="90e2d-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="90e2d-112">Die zweite Anweisung erstellt aus den Zeichenfolgenwerten, die der Benutzer im Benutzeroberflächenabschnitt **Add New Book** eingegeben hat, ein neues <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="90e2d-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="90e2d-113">Die letzte Anweisung fügt dem Datenanbieter in *L2DBForm.xaml* dieses neue Buchelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="90e2d-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="90e2d-114">Daraufhin aktualisiert die dynamische Datenbindung automatisch die Benutzeroberfläche mit diesem neuen Element. Zusätzlicher, vom Benutzer bereitgestellter Code ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90e2d-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="90e2d-115">Ereignishandler „OnRemove“</span><span class="sxs-lookup"><span data-stu-id="90e2d-115">OnRemove event handler</span></span>

<span data-ttu-id="90e2d-116">Der `OnRemove`-Handler ist aus zwei Gründen komplizierter als der `OnAddBook`-Handler.</span><span class="sxs-lookup"><span data-stu-id="90e2d-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="90e2d-117">Erstens: Das unformatierte XML enthält beibehaltenen Leerraum, sodass zusammen mit dem Bucheintrag auch  passende neue Zeilen entfernt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="90e2d-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="90e2d-118">Zweitens: Im Sinne der Bequemlichkeit wird die Auswahl, die auf dem gelöschten Element lag, auf das vorherige Element in der Liste zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="90e2d-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="90e2d-119">Die Hauptarbeit wird aber mit dem Entfernen des ausgewählten Buchelements von lediglich zwei Anweisungen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="90e2d-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="90e2d-120">Zunächst wird das dem aktuell ausgewählten Element im Listenfeld zugeordnete Buchelement abgerufen:</span><span class="sxs-lookup"><span data-stu-id="90e2d-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="90e2d-121">Anschließend wird dieses Element aus dem Datenanbieter gelöscht:</span><span class="sxs-lookup"><span data-stu-id="90e2d-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="90e2d-122">Auch hier stellt die dynamische Datenbindung sicher, dass die Benutzeroberfläche des Programms automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="90e2d-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="90e2d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90e2d-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="90e2d-124">Code</span><span class="sxs-lookup"><span data-stu-id="90e2d-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="90e2d-125">Kommentare</span><span class="sxs-lookup"><span data-stu-id="90e2d-125">Comments</span></span>

<span data-ttu-id="90e2d-126">Informationen zur zugeordneten XAML-Quelle für diese Handler finden Sie unter [L2DBForm.xaml.cs-Quellcode](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="90e2d-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90e2d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90e2d-127">See also</span></span>

- [<span data-ttu-id="90e2d-128">Exemplarische Vorgehensweise: LinqToXmlDataBinding-Beispiel</span><span class="sxs-lookup"><span data-stu-id="90e2d-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="90e2d-129">L2DBForm.xaml-Quellcode</span><span class="sxs-lookup"><span data-stu-id="90e2d-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
