---
title: 'Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 166eda4a9348188fa6e5048fd3ce41645cde4816
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053595"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="3fc49-102">Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fc49-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="3fc49-103">In diesem Beispiel wird die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet, um den IIS-Verwaltungsdienst auf dem lokalen Computer anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="3fc49-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fc49-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fc49-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="3fc49-105">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3fc49-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="3fc49-106">Er befindet sich in der Codeausschnittauswahl unter **Windows-Betriebssystem > Windows-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="3fc49-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="3fc49-107">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="3fc49-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fc49-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3fc49-108">Compiling the Code</span></span>  
 <span data-ttu-id="3fc49-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3fc49-109">This example requires:</span></span>  
  
- <span data-ttu-id="3fc49-110">Einen Projektverweis auf „System.serviceprocess.dll“.</span><span class="sxs-lookup"><span data-stu-id="3fc49-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="3fc49-111">Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace</span><span class="sxs-lookup"><span data-stu-id="3fc49-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="3fc49-112">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="3fc49-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="3fc49-113">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="3fc49-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3fc49-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="3fc49-114">Robust Programming</span></span>  
 <span data-ttu-id="3fc49-115">Die Standardeinstellung für die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft der <xref:System.ServiceProcess.ServiceController>-Klasse ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="3fc49-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="3fc49-116">Ändern Sie zum Verweisen auf die Windows-Dienste auf einem anderen Computer die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft in den Namen des entsprechenden Computers.</span><span class="sxs-lookup"><span data-stu-id="3fc49-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="3fc49-117">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="3fc49-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="3fc49-118">Der Dienst kann nicht angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="3fc49-118">The service cannot be paused.</span></span> <span data-ttu-id="3fc49-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="3fc49-119">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="3fc49-120">Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3fc49-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="3fc49-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="3fc49-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3fc49-122">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3fc49-122">.NET Framework Security</span></span>  
 <span data-ttu-id="3fc49-123">Die Steuerung von Diensten auf dem Computer kann mithilfe von <xref:System.ServiceProcess.ServiceControllerPermissionAccess> eingeschränkt werden, um Berechtigungen in <xref:System.ServiceProcess.ServiceControllerPermission> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3fc49-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="3fc49-124">Der Zugriff auf Dienstinformationen kann mithilfe von <xref:System.Security.Permissions.PermissionState> eingeschränkt werden, um Berechtigungen in <xref:System.Security.Permissions.SecurityPermission> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3fc49-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc49-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fc49-125">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="3fc49-126">How to: Fortsetzen eines Windows-Diensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fc49-126">How to: Continue a Windows Service (Visual Basic)</span></span>](how-to-continue-a-windows-service-visual-basic.md)
