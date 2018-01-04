---
title: "Gewusst wie: Angeben des Sicherheitskontexts für Dienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 9ce65358f6d63414dbe6798d3cc2464ee2741980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="0c211-102">Gewusst wie: Angeben des Sicherheitskontexts für Dienste</span><span class="sxs-lookup"><span data-stu-id="0c211-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="0c211-103">Standardmäßig werden Dienste in einem anderen Sicherheitskontext als dem des angemeldeten Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c211-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="0c211-104">Wird aufgerufen, der Dienst ausgeführt wird, im Rahmen des Standardkontos System `LocalSystem`, die erhalten sie unterschiedliche Zugriffsrechte auf Systemressourcen, als der vom Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0c211-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="0c211-105">Sie können dieses Verhalten, um ein anderes Benutzerkonto angeben, unter dem der Dienst ausgeführt werden soll, ändern.</span><span class="sxs-lookup"><span data-stu-id="0c211-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="0c211-106">Festlegen des Sicherheitskontexts durch Bearbeiten der <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> Eigenschaft für den Prozess, in dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c211-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="0c211-107">Diese Eigenschaft können Sie den Dienst auf einen der vier Kontotypen festlegen:</span><span class="sxs-lookup"><span data-stu-id="0c211-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="0c211-108">`User`, die bewirkt, dass des Systems für einen gültigen Benutzernamen und Kennwort aufgefordert werden, wenn der Dienst installiert ist und ausgeführt, im Kontext eines Kontos angegeben, die durch einen einzelnen Benutzer im Netzwerk wird;</span><span class="sxs-lookup"><span data-stu-id="0c211-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="0c211-109">`LocalService`, der ausgeführt wird, im Kontext eines Kontos, das als nicht berechtigte Benutzer auf dem lokalen Computer fungiert und Remoteservern werden anonyme Anmeldeinformationen alle Remoteserver; übergeben</span><span class="sxs-lookup"><span data-stu-id="0c211-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="0c211-110">`LocalSystem`, die im Kontext eines Kontos, das umfangreiche lokale Berechtigungen und stellt Anmeldeinformationen des Computers, auf alle RAS-Server ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0c211-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="0c211-111">`NetworkService`, die im Kontext eines Kontos ein, die als nicht berechtigte Benutzer auf dem lokalen Computer fungiert, und stellt die Anmeldeinformationen des Computers mit remote-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c211-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="0c211-112">Weitere Informationen finden Sie unter der <xref:System.ServiceProcess.ServiceAccount>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0c211-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="0c211-113">Um den Sicherheitskontext für einen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0c211-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="0c211-114">Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c211-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="0c211-115">Weitere Informationen finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="0c211-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="0c211-116">Im Designer Zugriff auf die `ProjectInstaller` Klasse, und klicken Sie auf das Dienstinstallationsprogramm-Prozess für den Dienst mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0c211-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c211-117">Für jede dienstanwendung sind mindestens zwei Installationskomponenten in der `ProjectInstaller` Klasse – eine, die die Prozesse für alle Dienste im Projekt und für jeden Dienst, der die Anwendung enthält einen Installer installiert.</span><span class="sxs-lookup"><span data-stu-id="0c211-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="0c211-118">In diesem Fall sollten Sie auswählen möchten <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="0c211-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="0c211-119">In der **Eigenschaften** legen die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> auf den entsprechenden Wert.</span><span class="sxs-lookup"><span data-stu-id="0c211-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c211-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c211-120">See Also</span></span>  
 [<span data-ttu-id="0c211-121">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="0c211-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="0c211-122">Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="0c211-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="0c211-123">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="0c211-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
