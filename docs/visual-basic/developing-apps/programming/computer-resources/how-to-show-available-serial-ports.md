---
title: 'Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: c7e5f797c1d098a3b2d01745b949ed50375ea7e8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345576"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="e0cf6-102">Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0cf6-102">How to: Show Available Serial Ports in Visual Basic</span></span>

<span data-ttu-id="e0cf6-103">In diesem Thema wird beschrieben, wie `My.Computer.Ports` zum Anzeigen der verfügbaren seriellen Ports eines Computers in Visual Basic verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in Visual Basic.</span></span>  
  
 <span data-ttu-id="e0cf6-104">Damit ein Benutzer auswählen kann, welcher Anschluss verwendet werden soll, werden die Namen der seriellen Anschlüsse in ein <xref:System.Windows.Forms.ListBox>-Steuerelement platziert.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0cf6-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0cf6-105">Example</span></span>  

 <span data-ttu-id="e0cf6-106">In diesem Beispiel werden alle Zeichenfolgen durchlaufen, die die `My.Computer.Ports.SerialPortNames`-Eigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="e0cf6-107">Diese Zeichenfolgen sind die Namen der auf dem Computer verfügbaren Anschlüsse.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="e0cf6-108">Üblicherweise wählt ein Benutzer aus der Liste der verfügbaren Anschlüsse aus, welchen seriellen Anschluss die Anwendung verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="e0cf6-109">In diesem Beispiel werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>-Steuerelement gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="e0cf6-110">Weitere Informationen finden Sie unter [ListBox-Steuerelement](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e0cf6-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 <span data-ttu-id="e0cf6-111">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e0cf6-112">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-112">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="e0cf6-113">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e0cf6-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0cf6-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e0cf6-114">Compiling the Code</span></span>  

 <span data-ttu-id="e0cf6-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e0cf6-115">This example requires:</span></span>  
  
- <span data-ttu-id="e0cf6-116">Ein Projektverweis auf „System.Windows.Forms.dll“.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-116">A project reference to System.Windows.Forms.dll.</span></span>  
  
- <span data-ttu-id="e0cf6-117">Zugriff auf die Member des <xref:System.Windows.Forms>-Namespace</span><span class="sxs-lookup"><span data-stu-id="e0cf6-117">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="e0cf6-118">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="e0cf6-119">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="e0cf6-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
- <span data-ttu-id="e0cf6-120">Dass Ihr Formular ein <xref:System.Windows.Forms.ListBox>-Steuerelement mit dem Namen `ListBox1` hat.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-120">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e0cf6-121">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="e0cf6-121">Robust Programming</span></span>  

 <span data-ttu-id="e0cf6-122">Sie müssen nicht das <xref:System.Windows.Forms.ListBox>-Steuerelement verwenden, um die Namen der verfügbaren seriellen Anschlüsse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-122">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="e0cf6-123">Stattdessen können Sie <xref:System.Windows.Forms.ComboBox> oder ein anderes Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-123">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="e0cf6-124">Wenn die Anwendung keine Antwort des Benutzers erfordert, können Sie ein <xref:System.Windows.Forms.TextBox>-Steuerungselement verwenden, um die Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-124">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0cf6-125">Die von `My.Computer.Ports.SerialPortNames` zurückgegebenen Anschlussnamen sind möglicherweise unter Windows 98 unzulässig.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-125">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="e0cf6-126">Verwenden Sie die Ausnahmebehandlung, um Anwendungsfehler zu verhindern – z.B die `Try...Catch...Finally`-Anweisung oder die `Using`-Anweisung beim Öffnen der Anschlüsse mithilfe der Anschlussnamen.</span><span class="sxs-lookup"><span data-stu-id="e0cf6-126">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cf6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0cf6-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="e0cf6-128">Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="e0cf6-128">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="e0cf6-129">Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="e0cf6-129">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="e0cf6-130">Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="e0cf6-130">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
