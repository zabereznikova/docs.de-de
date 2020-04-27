---
title: 'Vorgehensweise: Angeben des Sicherheitskontexts für Dienste'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
ms.openlocfilehash: dd2a9c4485e151d4cb1c9d5ae3a95a69fcc416d4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053585"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="1b30c-102">Vorgehensweise: Angeben des Sicherheitskontexts für Dienste</span><span class="sxs-lookup"><span data-stu-id="1b30c-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="1b30c-103">Standardmäßig werden Dienste in einem anderen Sicherheitskontext ausgeführt als dem des angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1b30c-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="1b30c-104">Dienste werden im Kontext des Standardsystemkontos, `LocalSystem`, ausgeführt, das ihnen andere Zugriffsberechtigungen für Systemressourcen erteilt als dem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1b30c-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="1b30c-105">Sie können dieses Verhalten ändern und ein anderes Benutzerkonto angeben, unter dem Ihr Dienst ausgeführt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="1b30c-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="1b30c-106">Der Sicherheitskontext lässt sich festlegen, indem Sie die Eigenschaft <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> für den Prozess bearbeiten, in dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b30c-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="1b30c-107">Mit dieser Eigenschaft können Sie den Dienst auf einen von vier Kontotypen festlegen:</span><span class="sxs-lookup"><span data-stu-id="1b30c-107">This property allows you to set the service to one of four account types:</span></span>  
  
- <span data-ttu-id="1b30c-108">`User`: Bewirkt, dass das System bei der Installation des Diensts zur Eingabe eines gültigen Benutzernamens und eines gültigen Kennworts auffordert und im Zusammenhang mit einem Konto ausgeführt wird, das von einem Benutzer im Netzwerk angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1b30c-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
- <span data-ttu-id="1b30c-109">`LocalService`: Wird im Zusammenhang mit einem Konto ausgeführt, das als nicht berechtigter Benutzer des lokalen Computers fungiert, und stellt für beliebige Remoteserver Anmeldeinformationen bereit.</span><span class="sxs-lookup"><span data-stu-id="1b30c-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
- <span data-ttu-id="1b30c-110">`LocalSystem`: Wird im Zusammenhang mit einem Konto ausgeführt, auf dem umfassende lokale Berechtigungen bereitgestellt werden, und stellt für beliebige Remoteserver die Anmeldeinformationen des Computers bereit.</span><span class="sxs-lookup"><span data-stu-id="1b30c-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
- <span data-ttu-id="1b30c-111">`NetworkService`: Wird im Zusammenhang mit einem Konto ausgeführt, das als nicht berechtigter Benutzer des lokalen Computers fungiert, und stellt für beliebige Remoteserver die Anmeldeinformationen des Computers bereit.</span><span class="sxs-lookup"><span data-stu-id="1b30c-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="1b30c-112">Weitere Informationen finden Sie unter der <xref:System.ServiceProcess.ServiceAccount>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1b30c-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="1b30c-113">Angeben des Sicherheitskontexts für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="1b30c-113">To specify the security context for a service</span></span>  
  
1. <span data-ttu-id="1b30c-114">Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="1b30c-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="1b30c-115">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="1b30c-115">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="1b30c-116">Greifen Sie im Designer auf die Klasse `ProjectInstaller` zu, und klicken Sie bei dem Prozess, mit dem Sie arbeiten, auf den Dienstprozessinstaller.</span><span class="sxs-lookup"><span data-stu-id="1b30c-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1b30c-117">Die Klasse `ProjectInstaller` enthält für jede Dienstanwendung mindestens zwei Installationskomponenten: eine Komponente, welche die Prozesse für sämtliche Dienste im Projekt installiert, und einen Installer für jeden in der App enthaltenen Dienst.</span><span class="sxs-lookup"><span data-stu-id="1b30c-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="1b30c-118">Wählen Sie in dieser Instanz <xref:System.ServiceProcess.ServiceProcessInstaller> aus.</span><span class="sxs-lookup"><span data-stu-id="1b30c-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3. <span data-ttu-id="1b30c-119">Legen Sie im Fenster **Eigenschaften**<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> auf den entsprechenden Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1b30c-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b30c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b30c-120">See also</span></span>

- [<span data-ttu-id="1b30c-121">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="1b30c-121">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="1b30c-122">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="1b30c-122">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="1b30c-123">How to: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="1b30c-123">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
