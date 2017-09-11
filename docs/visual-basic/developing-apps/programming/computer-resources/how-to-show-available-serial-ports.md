---
title: "Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bab6177c788a847b46586db19a525c1a1b36476d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="93861-102">Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93861-102">How to: Show Available Serial Ports in Visual Basic</span></span>
<span data-ttu-id="93861-103">Dieses Thema beschreibt, wie `My.Computer.Ports` zum Anzeigen der verfügbaren seriellen Anschlüsse eines Computers in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="93861-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="93861-104">Damit ein Benutzer auswählen kann, welcher Anschluss verwendet werden soll, werden die Namen der seriellen Anschlüsse in ein <xref:System.Windows.Forms.ListBox>-Steuerelement platziert.</span><span class="sxs-lookup"><span data-stu-id="93861-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93861-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93861-105">Example</span></span>  
 <span data-ttu-id="93861-106">In diesem Beispiel werden alle Zeichenfolgen durchlaufen, die die `My.Computer.Ports.SerialPortNames`-Eigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="93861-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="93861-107">Diese Zeichenfolgen sind die Namen der auf dem Computer verfügbaren Anschlüsse.</span><span class="sxs-lookup"><span data-stu-id="93861-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="93861-108">Üblicherweise wählt ein Benutzer aus der Liste der verfügbaren Anschlüsse aus, welchen seriellen Anschluss die Anwendung verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="93861-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="93861-109">In diesem Beispiel werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>-Steuerelement gespeichert.</span><span class="sxs-lookup"><span data-stu-id="93861-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="93861-110">Weitere Informationen finden Sie unter [ListBox-Steuerelement](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="93861-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="93861-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="93861-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span></span>  
  
 <span data-ttu-id="93861-112">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="93861-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="93861-113">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="93861-113">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="93861-114">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="93861-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93861-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="93861-115">Compiling the Code</span></span>  
 <span data-ttu-id="93861-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="93861-116">This example requires:</span></span>  
  
-   <span data-ttu-id="93861-117">Ein Projektverweis auf „System.Windows.Forms.dll“.</span><span class="sxs-lookup"><span data-stu-id="93861-117">A project reference to System.Windows.Forms.dll.</span></span>  
  
-   <span data-ttu-id="93861-118">Zugriff auf die Member des <xref:System.Windows.Forms>-Namespace</span><span class="sxs-lookup"><span data-stu-id="93861-118">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="93861-119">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="93861-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="93861-120">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="93861-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
-   <span data-ttu-id="93861-121">Dass Ihr Formular ein <xref:System.Windows.Forms.ListBox>-Steuerelement mit dem Namen `ListBox1` hat.</span><span class="sxs-lookup"><span data-stu-id="93861-121">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="93861-122">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="93861-122">Robust Programming</span></span>  
 <span data-ttu-id="93861-123">Sie müssen nicht das <xref:System.Windows.Forms.ListBox>-Steuerelement verwenden, um die Namen der verfügbaren seriellen Anschlüsse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93861-123">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="93861-124">Stattdessen können Sie <xref:System.Windows.Forms.ComboBox> oder ein anderes Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="93861-124">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="93861-125">Wenn die Anwendung keine Antwort des Benutzers erfordert, können Sie ein <xref:System.Windows.Forms.TextBox>-Steuerungselement verwenden, um die Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93861-125">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93861-126">Die von `My.Computer.Ports.SerialPortNames` zurückgegebenen Anschlussnamen sind möglicherweise unter Windows 98 unzulässig.</span><span class="sxs-lookup"><span data-stu-id="93861-126">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="93861-127">Verwenden Sie die Ausnahmebehandlung, um Anwendungsfehler zu verhindern – z.B die `Try...Catch...Finally`-Anweisung oder die `Using`-Anweisung beim Öffnen der Anschlüsse mithilfe der Anschlussnamen.</span><span class="sxs-lookup"><span data-stu-id="93861-127">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93861-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93861-128">See Also</span></span>  
 <span data-ttu-id="93861-129"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="93861-129"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="93861-130">[Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="93861-130">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="93861-131">[Vorgehensweise: Senden von Zeichenfolgen zu seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="93861-131">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="93861-132">Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="93861-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)

