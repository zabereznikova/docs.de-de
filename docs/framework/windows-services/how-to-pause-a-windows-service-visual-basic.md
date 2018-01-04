---
title: 'Gewusst wie: Anhalten von Windows-Diensten (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 90f2b01fae057a05cc71f77cecea3fdf85c832b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="ef478-102">Gewusst wie: Anhalten von Windows-Diensten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef478-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="ef478-103">Dieses Beispiel verwendet die <xref:System.ServiceProcess.ServiceController> Komponente so halten Sie die IIS-Verwaltungsdienst auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="ef478-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef478-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef478-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="ef478-105">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef478-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ef478-106">In der Codeausschnittauswahl befindet sich im **Windows-Betriebssystem > Windows-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="ef478-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="ef478-107">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="ef478-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef478-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ef478-108">Compiling the Code</span></span>  
 <span data-ttu-id="ef478-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ef478-109">This example requires:</span></span>  
  
-   <span data-ttu-id="ef478-110">Ein Projektverweis zu System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="ef478-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="ef478-111">Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace</span><span class="sxs-lookup"><span data-stu-id="ef478-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="ef478-112">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="ef478-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="ef478-113">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ef478-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ef478-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ef478-114">Robust Programming</span></span>  
 <span data-ttu-id="ef478-115">Die <xref:System.ServiceProcess.ServiceController.MachineName%2A> Eigenschaft von der <xref:System.ServiceProcess.ServiceController> Klasse ist der lokale Computer standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="ef478-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="ef478-116">Um Windows-Dienste auf einem anderen Computer verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A> -Eigenschaft auf den Namen des betreffenden Computers.</span><span class="sxs-lookup"><span data-stu-id="ef478-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="ef478-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="ef478-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ef478-118">Der Dienst kann nicht angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ef478-118">The service cannot be paused.</span></span> <span data-ttu-id="ef478-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="ef478-119">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="ef478-120">Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ef478-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="ef478-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="ef478-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ef478-122">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ef478-122">.NET Framework Security</span></span>  
 <span data-ttu-id="ef478-123">Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess> zum Festlegen von Berechtigungen der <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="ef478-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="ef478-124">Zugriff auf Dienstinformationen kann eingeschränkt werden, mithilfe der <xref:System.Security.Permissions.PermissionState> zum Festlegen von Berechtigungen der <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="ef478-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef478-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef478-125">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [<span data-ttu-id="ef478-126">Vorgehensweise: Fortsetzen eines Windows-Diensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef478-126">How to: Continue a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
