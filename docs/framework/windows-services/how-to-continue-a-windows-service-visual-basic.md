---
title: 'Vorgehensweise: Fortsetzen eines Windows-Diensts (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: a10e05b0460608a9e67ee4527adf80be3d47438e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053641"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="985ff-102">Vorgehensweise: Fortsetzen eines Windows-Diensts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="985ff-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="985ff-103">In diesem Beispiel wird die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet, um den IIS-Verwaltungsdienst auf dem lokalen Computer fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="985ff-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="985ff-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="985ff-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="985ff-105">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="985ff-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="985ff-106">Er befindet sich in der Codeausschnittauswahl unter **Windows-Betriebssystem > Windows-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="985ff-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="985ff-107">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="985ff-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="985ff-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="985ff-108">Compiling the Code</span></span>  
 <span data-ttu-id="985ff-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="985ff-109">This example requires:</span></span>  
  
- <span data-ttu-id="985ff-110">Einen Projektverweis auf „System.serviceprocess.dll“.</span><span class="sxs-lookup"><span data-stu-id="985ff-110">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="985ff-111">Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace</span><span class="sxs-lookup"><span data-stu-id="985ff-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="985ff-112">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="985ff-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="985ff-113">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="985ff-113">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="985ff-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="985ff-114">Robust Programming</span></span>  
 <span data-ttu-id="985ff-115">Die Standardeinstellung für die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft der <xref:System.ServiceProcess.ServiceController>-Klasse ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="985ff-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="985ff-116">Ändern Sie zum Verweisen auf die Windows-Dienste auf einem anderen Computer die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft in den Namen des entsprechenden Computers.</span><span class="sxs-lookup"><span data-stu-id="985ff-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="985ff-117">Die <xref:System.ServiceProcess.ServiceController.Continue%2A>-Methode für einen Dienst kann erst aufgerufen werden, wenn der Status des Dienstcontrollers <xref:System.ServiceProcess.ServiceControllerStatus.Paused> lautet.</span><span class="sxs-lookup"><span data-stu-id="985ff-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="985ff-118">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="985ff-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="985ff-119">Der Dienst kann nicht fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="985ff-119">The service cannot be resumed.</span></span> <span data-ttu-id="985ff-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="985ff-120">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="985ff-121">Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="985ff-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="985ff-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="985ff-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="985ff-123">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="985ff-123">.NET Framework Security</span></span>  
 <span data-ttu-id="985ff-124">Die Steuerung von Diensten auf dem Computer kann mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess>-Enumeration eingeschränkt werden, um Berechtigungen in der <xref:System.ServiceProcess.ServiceControllerPermission>-Klasse festzulegen.</span><span class="sxs-lookup"><span data-stu-id="985ff-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="985ff-125">Der Zugriff auf Dienstinformationen kann mithilfe der <xref:System.Security.Permissions.PermissionState>-Enumeration eingeschränkt werden, um Berechtigungen in der <xref:System.Security.Permissions.SecurityPermission>-Klasse festzulegen.</span><span class="sxs-lookup"><span data-stu-id="985ff-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="985ff-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="985ff-126">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="985ff-127">How to: Anhalten von Windows-Diensten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="985ff-127">How to: Pause a Windows Service (Visual Basic)</span></span>](how-to-pause-a-windows-service-visual-basic.md)
