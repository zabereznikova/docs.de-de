---
title: 'Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)'
description: Hier erfahren Sie, wie Sie die ServiceController-Komponente verwenden, um einen Windows-Dienst (z. B. den IIS-Verwaltungsdienst) auf einem lokalen Computer mit Visual Basic anzuhalten.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
ms.openlocfilehash: 19919a8b0a289f0e88eb136d8c010a036e84cbec
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608503"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="b23b9-103">Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23b9-103">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="b23b9-104">In diesem Beispiel wird die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet, um den IIS-Verwaltungsdienst auf dem lokalen Computer anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="b23b9-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b23b9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b23b9-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="b23b9-106">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b23b9-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="b23b9-107">Er befindet sich in der Codeausschnittauswahl unter **Windows-Betriebssystem > Windows-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="b23b9-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="b23b9-108">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="b23b9-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b23b9-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b23b9-109">Compiling the Code</span></span>  
 <span data-ttu-id="b23b9-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b23b9-110">This example requires:</span></span>  
  
- <span data-ttu-id="b23b9-111">Einen Projektverweis auf „System.serviceprocess.dll“.</span><span class="sxs-lookup"><span data-stu-id="b23b9-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="b23b9-112">Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace</span><span class="sxs-lookup"><span data-stu-id="b23b9-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="b23b9-113">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="b23b9-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="b23b9-114">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="b23b9-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b23b9-115">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b23b9-115">Robust Programming</span></span>  
 <span data-ttu-id="b23b9-116">Die Standardeinstellung für die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft der <xref:System.ServiceProcess.ServiceController>-Klasse ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="b23b9-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="b23b9-117">Ändern Sie zum Verweisen auf die Windows-Dienste auf einem anderen Computer die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft in den Namen des entsprechenden Computers.</span><span class="sxs-lookup"><span data-stu-id="b23b9-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="b23b9-118">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b23b9-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="b23b9-119">Der Dienst kann nicht angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b23b9-119">The service cannot be paused.</span></span> <span data-ttu-id="b23b9-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="b23b9-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="b23b9-121">Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b23b9-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="b23b9-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="b23b9-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b23b9-123">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b23b9-123">.NET Framework Security</span></span>  
 <span data-ttu-id="b23b9-124">Die Steuerung von Diensten auf dem Computer kann mithilfe von <xref:System.ServiceProcess.ServiceControllerPermissionAccess> eingeschränkt werden, um Berechtigungen in <xref:System.ServiceProcess.ServiceControllerPermission> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b23b9-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="b23b9-125">Der Zugriff auf Dienstinformationen kann mithilfe von <xref:System.Security.Permissions.PermissionState> eingeschränkt werden, um Berechtigungen in <xref:System.Security.Permissions.SecurityPermission> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b23b9-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23b9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b23b9-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="b23b9-127">How to: Fortsetzen eines Windows-Diensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23b9-127">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
