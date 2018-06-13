---
title: Clientanwendungsdienste
ms.date: 03/30/2017
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
ms.openlocfilehash: d67b7467bdacdfca054d0ecd11a81c7d25b158f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743224"
---
# <a name="client-application-services"></a><span data-ttu-id="ba788-102">Clientanwendungsdienste</span><span class="sxs-lookup"><span data-stu-id="ba788-102">Client Application Services</span></span>
<span data-ttu-id="ba788-103">Clientanwendungsdienste erleichtern Ihnen Erstellung von Windows-basierten Anwendungen, die die [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anmelde-, -Rollen- und -Profilanwendungsdienste verwenden, die in den Microsoft ASP.NET 2.0 AJAX-Erweiterungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ba788-103">Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions.</span></span> <span data-ttu-id="ba788-104">Diese Dienste ermöglichen mehreren web- und Windows-basierten Anwendungen die gemeinsame Nutzung von Benutzerinformationen und Benutzerverwaltungsfunktionen von einem einzelnen Server aus.</span><span class="sxs-lookup"><span data-stu-id="ba788-104">These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server.</span></span> <span data-ttu-id="ba788-105">Beispielsweise können Sie mithilfe dieser Dienste folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="ba788-105">For example, you can use these services to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ba788-106">Authentifizieren von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="ba788-106">Authenticate a user.</span></span> <span data-ttu-id="ba788-107">Mithilfe des Authentifizierungsdiensts können Sie die Identität eines Benutzers überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ba788-107">You can use the authentication service to verify a user's identity.</span></span>  
  
-   <span data-ttu-id="ba788-108">Bestimmen der Rolle oder Rollen eines authentifizierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ba788-108">Determine the role or roles of an authenticated user.</span></span> <span data-ttu-id="ba788-109">Mithilfe des Rollendiensts können Sie die Benutzeroberfläche Ihrer Anwendung in Abhängigkeit von der Rolle des Benutzers ändern.</span><span class="sxs-lookup"><span data-stu-id="ba788-109">You can use the roles service to change the user interface of your application depending on the user's role.</span></span> <span data-ttu-id="ba788-110">Beispielsweise können Sie zusätzliche Funktionen für Benutzer bereitstellen, die in einer Administratorrolle sind.</span><span class="sxs-lookup"><span data-stu-id="ba788-110">For example, you can provide additional features for users who are in an administrator role.</span></span>  
  
-   <span data-ttu-id="ba788-111">Speichern von und Zugreifen auf benutzerspezifische Anwendungseinstellungen auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="ba788-111">Store and access per-user application settings located on the server.</span></span> <span data-ttu-id="ba788-112">Mithilfe des Webeinstellungendiensts (auch als Profildienst bekannt) können Sie Einstellungen zwischen mehreren Anwendungen und Speicherorten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="ba788-112">You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.</span></span>  
  
 <span data-ttu-id="ba788-113">Clientanwendungsdienste nutzen das Erweiterbarkeitsmodell des Webdiensts durch Clientdienstanbieter, die Sie in Ihren Anwendungskonfigurationsdateien angeben können.</span><span class="sxs-lookup"><span data-stu-id="ba788-113">Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files.</span></span> <span data-ttu-id="ba788-114">Diese Dienstanbieter umfassen Offlinefunktionalitäten, die einen lokalen Cache für Authentifizierung, Rollen und Einstellungsdaten verwenden, wenn keine Netzwerkverbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ba788-114">These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.</span></span>  
  
 <span data-ttu-id="ba788-115">Weitere Informationen zu den [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anwendungsdiensten finden Sie unter [Übersicht über ASP.NET-Anwendungsdienste](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span><span class="sxs-lookup"><span data-stu-id="ba788-115">For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba788-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba788-116">In This Section</span></span>  
 [<span data-ttu-id="ba788-117">Übersicht über Clientanwendungsdienste</span><span class="sxs-lookup"><span data-stu-id="ba788-117">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 <span data-ttu-id="ba788-118">Beschreibt die Funktionen, die durch die Clientanwendungs-Dienstanbieter verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ba788-118">Describes the features available through the client application service providers.</span></span>  
  
 [<span data-ttu-id="ba788-119">Vorgehensweise: Konfigurieren von Clientanwendungsdiensten</span><span class="sxs-lookup"><span data-stu-id="ba788-119">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 <span data-ttu-id="ba788-120">Beschreibt, wie Sie den Visual Studio-Projekt-Designer zum Aktivieren und Konfigurieren von Anwendungsdiensten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba788-120">Describes how to use the Visual Studio project designer to enable and configuration application services.</span></span> <span data-ttu-id="ba788-121">Beschreibt außerdem die entsprechenden Änderungen an Ihrer Datei "App.config".</span><span class="sxs-lookup"><span data-stu-id="ba788-121">Also describes the corresponding changes to your App.config file.</span></span>  
  
 [<span data-ttu-id="ba788-122">Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten</span><span class="sxs-lookup"><span data-stu-id="ba788-122">How to: Implement User Login with Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 <span data-ttu-id="ba788-123">Beschreibt, wie Sie einen Benutzer überprüfen, wenn Ihre Anwendung so konfiguriert ist, dass sie einen Clientauthentifizierungs-Dienstanbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba788-123">Describes how to validate a user when your application is configured to use a client authentication service provider.</span></span>  
  
 [<span data-ttu-id="ba788-124">Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten</span><span class="sxs-lookup"><span data-stu-id="ba788-124">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 <span data-ttu-id="ba788-125">Beschreibt, wie alle Funktionen von Clientanwendungsdiensten in einer einzigen Anwendung kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ba788-125">Describes how to combine all client application services features in a single application.</span></span> <span data-ttu-id="ba788-126">Diese exemplarische Vorgehensweise bietet Anleitungen von Anfang bis Ende.</span><span class="sxs-lookup"><span data-stu-id="ba788-126">This walkthrough provides end-to-end guidance.</span></span> <span data-ttu-id="ba788-127">Beispielsweise enthält sie Anweisungen zum Erstellen einer ASP.NET-Webdienstanwendung, mit der Sie Clientanwendungsdienste testen können.</span><span class="sxs-lookup"><span data-stu-id="ba788-127">For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ba788-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="ba788-128">Reference</span></span>  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a><span data-ttu-id="ba788-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba788-129">See Also</span></span>  
 [<span data-ttu-id="ba788-130">Übersicht über die ASP.NET-Anwendungsdienste</span><span class="sxs-lookup"><span data-stu-id="ba788-130">ASP.NET Application Services Overview</span></span>](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [<span data-ttu-id="ba788-131">Verwenden der Formularauthentifizierung mit Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="ba788-131">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [<span data-ttu-id="ba788-132">Verwenden von Rolleninformationen mit Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="ba788-132">Using Roles Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [<span data-ttu-id="ba788-133">Verwenden von Profilinformationen mit Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="ba788-133">Using Profile Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [<span data-ttu-id="ba788-134">Authentifizierung in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ba788-134">ASP.NET Authentication</span></span>](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 <span data-ttu-id="ba788-135">[Verwalten der Autorisierung mithilfe von Rollen](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span><span class="sxs-lookup"><span data-stu-id="ba788-135">[Managing Authorization Using Roles](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span></span>  
 [<span data-ttu-id="ba788-136">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba788-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)
