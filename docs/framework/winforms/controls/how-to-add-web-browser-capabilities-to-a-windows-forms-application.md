---
title: Webbrowser Funktionen zur APP hinzufügen
description: Erfahren Sie, wie Sie mit dem Webbrowser-Steuerelement einer Windows Forms Anwendung Webbrowser Funktionen hinzufügen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: a5a33961ac8301bda86bb5f34e65ac159308987f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174548"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="30b6d-103">Vorgehensweise beim Hinzufügen von Webbrowser Funktionen zu einer Windows Forms Anwendung</span><span class="sxs-lookup"><span data-stu-id="30b6d-103">How to add web browser capabilities to a Windows Forms application</span></span>

<span data-ttu-id="30b6d-104">Mit dem <xref:System.Windows.Forms.WebBrowser>-Steuerelement können Sie Webbrowserfunktionalität in Ihre Anwendung einbinden.</span><span class="sxs-lookup"><span data-stu-id="30b6d-104">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="30b6d-105">Das Steuerelement verhält sich standardmäßig wie ein Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="30b6d-105">The control works like a Web browser by default.</span></span> <span data-ttu-id="30b6d-106">Nach dem Laden einer Anfangs-URL durch Festlegen der <xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft können Sie auf Hyperlinks klicken oder mit den entsprechenden Tastenkombinationen vorwärts oder rückwärts durch den Navigationsverlauf navigieren.</span><span class="sxs-lookup"><span data-stu-id="30b6d-106">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="30b6d-107">Über das Kontextmenü, das durch Klicken mit der rechten Maustaste angezeigt wird, können standardmäßig zusätzliche Browserfunktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30b6d-107">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="30b6d-108">Sie können auch neue Dokumente öffnen, indem Sie sie auf dem Steuerelement ablegen.</span><span class="sxs-lookup"><span data-stu-id="30b6d-108">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="30b6d-109">Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse, mit denen Sie ähnliche Benutzeroberflächenfeatures wie in Internet Explorer implementieren können.</span><span class="sxs-lookup"><span data-stu-id="30b6d-109">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>

<span data-ttu-id="30b6d-110">Im folgenden Beispielcode werden eine Adressleiste, typische Browserschaltflächen, ein Menü **Datei**, eine Statusleiste und eine Titelleiste mit dem Titel der aktuellen Seite implementiert.</span><span class="sxs-lookup"><span data-stu-id="30b6d-110">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>

## <a name="example"></a><span data-ttu-id="30b6d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30b6d-111">Example</span></span>

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a><span data-ttu-id="30b6d-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="30b6d-112">Compile the code</span></span>

<span data-ttu-id="30b6d-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="30b6d-113">This example requires:</span></span>

- <span data-ttu-id="30b6d-114">Verweise auf die Assemblys `System`, `System.Drawing` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="30b6d-114">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="30b6d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30b6d-115">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="30b6d-116">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="30b6d-116">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
