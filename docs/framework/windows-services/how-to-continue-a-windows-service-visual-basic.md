---
title: 'Gewusst wie: Fortsetzen eines Windows-Diensts (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 73b16a5e5834f7279ae551d4e7efd26cc86c1d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="73765-102">Gewusst wie: Fortsetzen eines Windows-Diensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73765-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="73765-103">Dieses Beispiel verwendet die <xref:System.ServiceProcess.ServiceController> Komponente, für die IIS-Verwaltungsdienst auf dem lokalen Computer zu fortfahren.</span><span class="sxs-lookup"><span data-stu-id="73765-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73765-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73765-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="73765-105">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73765-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="73765-106">In der Codeausschnittauswahl befindet sich im **Windows-Betriebssystem > Windows-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="73765-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="73765-107">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="73765-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73765-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="73765-108">Compiling the Code</span></span>  
 <span data-ttu-id="73765-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="73765-109">This example requires:</span></span>  
  
-   <span data-ttu-id="73765-110">Ein Projektverweis zu System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="73765-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="73765-111">Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace</span><span class="sxs-lookup"><span data-stu-id="73765-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="73765-112">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="73765-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="73765-113">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="73765-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="73765-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="73765-114">Robust Programming</span></span>  
 <span data-ttu-id="73765-115">Die <xref:System.ServiceProcess.ServiceController.MachineName%2A> Eigenschaft von der <xref:System.ServiceProcess.ServiceController> Klasse ist der lokale Computer standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="73765-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="73765-116">Um Windows-Dienste auf einem anderen Computer verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A> -Eigenschaft auf den Namen des betreffenden Computers.</span><span class="sxs-lookup"><span data-stu-id="73765-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="73765-117">Sie können nicht aufgerufen werden der <xref:System.ServiceProcess.ServiceController.Continue%2A> Methode für einen Dienst, bis der Status des Controllers ist <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="73765-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="73765-118">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="73765-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="73765-119">Der Dienst kann nicht fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="73765-119">The service cannot be resumed.</span></span> <span data-ttu-id="73765-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="73765-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="73765-121">Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="73765-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="73765-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="73765-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="73765-123">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="73765-123">.NET Framework Security</span></span>  
 <span data-ttu-id="73765-124">Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess> Enumeration zum Festlegen von Berechtigungen der <xref:System.ServiceProcess.ServiceControllerPermission> Klasse.</span><span class="sxs-lookup"><span data-stu-id="73765-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="73765-125">Zugriff auf Dienstinformationen kann eingeschränkt werden, mithilfe der <xref:System.Security.Permissions.PermissionState> Enumeration zum Festlegen von Berechtigungen der <xref:System.Security.Permissions.SecurityPermission> Klasse.</span><span class="sxs-lookup"><span data-stu-id="73765-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73765-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73765-126">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [<span data-ttu-id="73765-127">Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73765-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
