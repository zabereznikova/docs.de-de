---
title: 'Vorgehensweise: Überwachen von Windows Communication Foundation-Sicherheitsereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 186dd4a7fc2beae848e5cbd167a204352ee6ed4e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601295"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="dd1a0-102">Vorgehensweise: Überwachen von Windows Communication Foundation-Sicherheitsereignissen</span><span class="sxs-lookup"><span data-stu-id="dd1a0-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="dd1a0-103">Mit Windows Communication Foundation (WCF) können Sie Sicherheitsereignisse im Windows-Ereignisprotokoll protokollieren, die mit dem Windows Ereignisanzeige angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="dd1a0-104">In diesem Thema wird erläutert, wie eine Anwendung so eingerichtet werden kann, dass Sicherheitsereignisse protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="dd1a0-105">Weitere Informationen zur WCF- [Überwachung finden Sie](auditing-security-events.md)unter Überwachung.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-105">For more information about WCF auditing, see [Auditing](auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="dd1a0-106">So überwachen Sie Sicherheitsereignisse im Code</span><span class="sxs-lookup"><span data-stu-id="dd1a0-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="dd1a0-107">Geben Sie den Speicherort des Überwachungsprotokolls an.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-107">Specify the audit log location.</span></span> <span data-ttu-id="dd1a0-108">Legen Sie hierzu die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>-Klasse auf einen der <xref:System.ServiceModel.AuditLogLocation>-Enumerationswerte fest, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="dd1a0-109">Die- <xref:System.ServiceModel.AuditLogLocation> Enumeration besitzt drei Werte: `Application` , `Security` oder `Default` .</span><span class="sxs-lookup"><span data-stu-id="dd1a0-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="dd1a0-110">Mithilfe des Werts wird eines der in der Ereignisanzeige angezeigten Protokolle angegeben: entweder das Sicherheits- oder das Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="dd1a0-111">Bei Verwendung des `Default`-Werts ist das tatsächliche Protokoll vom Betriebssystem abhängig, unter dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="dd1a0-112">Ist bei aktivierter Überwachung kein Protokollspeicherort angegeben, wird für Plattformen, von denen das Schreiben in das Sicherheitsprotokoll unterstützt wird, standardmäßig das `Security`-Protokoll verwendet. Andernfalls wird das `Application`-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="dd1a0-113">Standardmäßig unterstützen nur Windows Server 2003 und Windows Vista das Schreiben in das Sicherheitsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-113">Only Windows Server 2003 and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="dd1a0-114">Richten Sie die zu überwachenden Ereignistypen ein.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-114">Set up the types of events to audit.</span></span> <span data-ttu-id="dd1a0-115">Ereignisse auf Dienstebene sowie Autorisierungsereignisse auf Nachrichtenebene können gleichzeitig überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="dd1a0-116">Legen Sie hierzu die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>-Eigenschaft oder die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>-Eigenschaft auf einen der <xref:System.ServiceModel.AuditLevel>-Enumerationswerte fest, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="dd1a0-117">Geben Sie an, ob Fehler bei Protokollüberwachungsereignissen unterdrückt oder für die Anwendung verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="dd1a0-118">Legen Sie die <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>-Eigenschaft entweder auf `true` oder auf `false` fest, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="dd1a0-119">Die standardmäßige `SuppressAuditFailure`-Eigenschaft ist `true`. Die Anwendung wird also durch einen Fehler bei der Überwachung nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="dd1a0-120">Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="dd1a0-121">Für jede erfolgreiche Überwachung wird eine ausführliche Ablaufverfolgung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="dd1a0-122">Für jeden Überwachungsfehler wird eine Ablaufverfolgung auf Fehlerebene geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="dd1a0-123">Löschen Sie das vorhandene <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> aus der Verhaltensauflistung, die sich in der Beschreibung eines <xref:System.ServiceModel.ServiceHost> befindet.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="dd1a0-124">Der Zugriff auf die Verhaltensauflistung erfolgt über die <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Eigenschaft, auf die wiederum über die <xref:System.ServiceModel.ServiceHostBase.Description%2A>-Eigenschaft zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="dd1a0-125">Fügen Sie der gleichen Auflistung anschließend das neue <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> hinzu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="dd1a0-126">So richten Sie die Überwachung in der Konfiguration ein</span><span class="sxs-lookup"><span data-stu-id="dd1a0-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="dd1a0-127">Fügen Sie [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) dem- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) Abschnitt der Datei "Web. config" ein-Element hinzu, um die Überwachung in der Konfiguration einzurichten.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-127">To set up auditing in configuration, add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="dd1a0-128">Fügen Sie dann ein [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) -Element hinzu, und legen Sie die verschiedenen Attribute fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-128">Then add a [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="dd1a0-129">Geben Sie das Verhalten für den Dienst an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="dd1a0-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd1a0-130">Example</span></span>  
 <span data-ttu-id="dd1a0-131">Mithilfe des folgenden Codes wird eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse erstellt, und der Verhaltensauflistung wird ein neues <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="dd1a0-132">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dd1a0-132">.NET Framework Security</span></span>  
 <span data-ttu-id="dd1a0-133">Durch Festlegen der <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>-Eigenschaft auf `true` werden Fehler beim Generieren von Sicherheitsüberwachungen unterdrückt. (Bei Verwendung von `false` wird eine Ausnahme ausgelöst).</span><span class="sxs-lookup"><span data-stu-id="dd1a0-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="dd1a0-134">Wenn Sie jedoch die folgende Windows-Eigenschaft für die **lokale Sicherheitseinstellung** aktivieren, führt ein Fehler beim Generieren von Überwachungs Ereignissen dazu, dass Windows sofort heruntergefahren wird:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="dd1a0-135">**Überwachung: System sofort herunterfahren, wenn Sicherheitsüberprüfungen nicht protokolliert werden können**</span><span class="sxs-lookup"><span data-stu-id="dd1a0-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="dd1a0-136">Um die-Eigenschaft festzulegen, öffnen Sie das Dialogfeld **Lokale Sicherheitseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="dd1a0-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="dd1a0-137">Klicken Sie unter **Sicherheitseinstellungen**auf **lokale Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="dd1a0-138">Klicken Sie dann auf **Sicherheitsoptionen**.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="dd1a0-139">Wenn die <xref:System.ServiceModel.AuditLogLocation> -Eigenschaft auf festgelegt ist <xref:System.ServiceModel.AuditLogLocation.Security> und die Überwachung des **Objekt Zugriffs** in der **lokalen Sicherheitsrichtlinie**nicht festgelegt ist, werden Überwachungs Ereignisse nicht in das Sicherheitsprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="dd1a0-140">Es wird zwar kein Fehler zurückgegeben, doch die Überwachungseinträge werden nicht in das Sicherheitsprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd1a0-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd1a0-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="dd1a0-142">Auditing</span><span class="sxs-lookup"><span data-stu-id="dd1a0-142">Auditing</span></span>](auditing-security-events.md)
