---
title: 'Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: 38e3c62aaf0e87860732bcb12c61da69b1c4346d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="ccf8c-102">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="ccf8c-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>
<span data-ttu-id="ccf8c-103">Den Zugriff auf Ressourcen auf einem Windows-Domänencomputer zu kontrollieren gehört zu den grundlegenden Sicherheitsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="ccf8c-104">So sollten zum Beispiel nur bestimmte Benutzer vertrauliche Daten wie Lohnlisten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="ccf8c-105">In diesem Thema wird erklärt, wie Sie den Zugriff auf eine Methode beschränken können, indem Sie es zur Voraussetzung machen, dass die entsprechenden Benutzer einer vordefinierten Gruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="ccf8c-106">Ein funktionierendes Beispiel finden Sie unter [Zugriff auf Dienstvorgänge autorisieren](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ccf8c-106">For a working sample, see [Authorizing Access to Service Operations](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="ccf8c-107">Diese Aufgabe umfasst zwei separate Schritte.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="ccf8c-108">Zuerst wird die Gruppe erstellt und mit Benutzern gefüllt.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="ccf8c-109">Anschließend wird in einem zweiten Schritt die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse angewendet, um die Gruppe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="ccf8c-110">So erstellen Sie eine Windows-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ccf8c-110">To create a Windows group</span></span>  
  
1.  <span data-ttu-id="ccf8c-111">Öffnen der **Computerverwaltung** Konsole.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-111">Open the **Computer Management** console.</span></span>  
  
2.  <span data-ttu-id="ccf8c-112">Klicken Sie im linken Bereich auf **lokale Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="ccf8c-113">Mit der rechten Maustaste **Gruppen**, und klicken Sie auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4.  <span data-ttu-id="ccf8c-114">In der **Gruppenname** geben einen Namen für die neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5.  <span data-ttu-id="ccf8c-115">In der **Beschreibung** Geben Sie eine Beschreibung der neuen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-115">In the **Description** box, type a description of the new group.</span></span>  
  
6.  <span data-ttu-id="ccf8c-116">Klicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen von neuer Mitgliedern der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-116">Click the **Add** button to add new members to the group.</span></span>  
  
7.  <span data-ttu-id="ccf8c-117">Falls Sie sich selbst zur Gruppe hinzugefügt haben und den folgenden Code testen möchten, müssen Sie sich vom Computer abmelden und dann wieder anmelden, damit Sie in die Gruppe aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="ccf8c-118">So fordern Sie die Benutzermitgliedschaft an</span><span class="sxs-lookup"><span data-stu-id="ccf8c-118">To demand user membership</span></span>  
  
1.  <span data-ttu-id="ccf8c-119">Öffnen Sie die Windows Communication Foundation (WCF)-Codedatei, die den implementierten dienstvertragscode enthält.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-119">Open the Windows Communication Foundation (WCF) code file that contains the implemented service contract code.</span></span> <span data-ttu-id="ccf8c-120">Weitere Informationen zu einen Vertrag implementieren, finden Sie unter [implementieren Dienstverträge](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ccf8c-120">For more information about implementing a contract, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="ccf8c-121">Wenden Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut auf jede Methode an, die nur für eine bestimmte Gruppe zugelassen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="ccf8c-122">Legen Sie für die <xref:System.Security.Permissions.SecurityAttribute.Action%2A>-Eigenschaft den Wert <xref:System.Security.Permissions.SecurityAction.Demand> fest, und setzen Sie die <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>-Eigenschaft auf den Namen der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="ccf8c-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ccf8c-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="ccf8c-124">Wenn Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut auf einen Vertrag anwenden, wird eine <xref:System.Security.SecurityException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="ccf8c-125">Das Attribut kann nur auf Methodenebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="ccf8c-126">Steuern des Zugriffs auf eine Methode mithilfe eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ccf8c-126">Using a Certificate to Control Access to a Method</span></span>  
 <span data-ttu-id="ccf8c-127">Sie können mit der `PrincipalPermissionAttribute`-Klasse auch dann den Zugriff auf eine Methode steuern, wenn es sich bei den Clientanmeldeinformationen um ein Zertifikat handelt.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="ccf8c-128">Hierfür müssen Sie den Antragsteller und den Fingerabdruck des Zertifikats kennen.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="ccf8c-129">Um ein Zertifikat für die zugehörigen Eigenschaften untersuchen zu können, finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="ccf8c-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="ccf8c-130">Den Fingerabdruckwert finden Sie unter [wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="ccf8c-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="ccf8c-131">So steuern Sie den Zugriff mithilfe eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ccf8c-131">To control access using a certificate</span></span>  
  
1.  <span data-ttu-id="ccf8c-132">Wenden Sie die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse auf die Methode an, für die der Zugriff eingeschränkt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2.  <span data-ttu-id="ccf8c-133">Setzen Sie die Aktion des Attributs auf <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="ccf8c-134">Verwenden Sie für die `Name`-Eigenschaft eine Zeichenfolge mit dem Antragstellernamen und dem Fingerabdruck des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="ccf8c-135">Trennen Sie die beiden Werte durch ein Semikolon und ein Leerzeichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccf8c-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  <span data-ttu-id="ccf8c-136">Legen Sie für die <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>-Eigenschaft den Wert <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> wie im folgenden Konfigurationsbeispiel gezeigt fest:</span><span class="sxs-lookup"><span data-stu-id="ccf8c-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="ccf8c-137">Durch den Wert `UseAspNetRoles` wird angegeben, dass mit der `Name`-Eigenschaft von `PrincipalPermissionAttribute` ein Zeichenfolgenvergleich durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="ccf8c-138">Wenn ein Zertifikat als Clientanmeldeinformationen verwendet wird, verkettet standardmäßig WCF gemeinsame Zertifikatsname und den Fingerabdruck mit einem Semikolon, um einen eindeutigen Wert für die primäre Identität des Clients zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-138">When a certificate is used as a client credential, by default WCF concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="ccf8c-139">Sofern für den Dienst `UseAspNetRoles` als `PrincipalPermissionMode` gewählt wurde, wird dieser Wert für die primäre Identität mit dem Wert der `Name`-Eigenschaft verglichen, um die Zugriffsrechte des Benutzers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ccf8c-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="ccf8c-140">Sie können alternativ wie im folgenden Beispiel auch die <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>-Eigenschaft im Code festlegen, wenn Sie einen selbst gehosteten Dienst erstellen:</span><span class="sxs-lookup"><span data-stu-id="ccf8c-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ccf8c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccf8c-141">See Also</span></span>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.SecurityAction.Demand>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>  
 [<span data-ttu-id="ccf8c-142">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="ccf8c-142">Authorizing Access to Service Operations</span></span>](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="ccf8c-143">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ccf8c-143">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="ccf8c-144">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="ccf8c-144">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
