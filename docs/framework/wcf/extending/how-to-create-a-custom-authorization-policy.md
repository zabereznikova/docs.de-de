---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Autorisierungsrichtlinie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: fef7aa531c946ecacef30bb79f2362bad4d375ed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256026"
---
# <a name="how-to-create-a-custom-authorization-policy"></a><span data-ttu-id="1417c-102">Vorgehensweise: Erstellen einer benutzerdefinierten Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1417c-102">How to: Create a Custom Authorization Policy</span></span>

<span data-ttu-id="1417c-103">Die Identitäts Modell Infrastruktur in Windows Communication Foundation (WCF) unterstützt ein Anspruchs basiertes Autorisierungs Modell.</span><span class="sxs-lookup"><span data-stu-id="1417c-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports a claim-based authorization model.</span></span> <span data-ttu-id="1417c-104">Ansprüche werden aus Token extrahiert, wahlweise von der benutzerdefinierten Autorisierungsrichtlinie verarbeitet und in einen <xref:System.IdentityModel.Policy.AuthorizationContext> platziert, der dann untersucht werden kann, um Autorisierungsentscheidungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="1417c-104">Claims are extracted from tokens, optionally processed by custom authorization policy, and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext> that can then be examined to make authorization decisions.</span></span> <span data-ttu-id="1417c-105">Eine benutzerdefinierte Richtlinie kann zum Transformieren von Ansprüchen von eingehenden Token in von der Anwendung erwartete Ansprüche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1417c-105">A custom policy can be used to transform claims from incoming tokens into claims expected by the application.</span></span> <span data-ttu-id="1417c-106">Auf diese Weise kann die Anwendungsschicht von den Details zu den unterschiedlichen Ansprüchen isoliert werden, die von den verschiedenen Tokentypen bereitgestellt werden, die von WCF unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1417c-106">In this way, the application layer can be insulated from the details on the differing claims served up by the different token types that WCF supports.</span></span> <span data-ttu-id="1417c-107">In diesem Thema wird gezeigt, wie eine benutzerdefinierte Autorisierungsrichtlinie implementiert und wie diese Richtlinie einer Sammlung von Richtlinien, die von einem Dienst verwendet werden, hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1417c-107">This topic shows how to implement a custom authorization policy and how to add that policy to the collection of policies used by a service.</span></span>  
  
### <a name="to-implement-a-custom-authorization-policy"></a><span data-ttu-id="1417c-108">So implementieren Sie eine benutzerdefinierte Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1417c-108">To implement a custom authorization policy</span></span>  
  
1. <span data-ttu-id="1417c-109">Definieren Sie eine neue Klasse, die von <xref:System.IdentityModel.Policy.IAuthorizationPolicy> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1417c-109">Define a new class that derives from <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2. <span data-ttu-id="1417c-110">Implementieren Sie die schreibgeschützte <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A>-Eigenschaft, indem Sie eine eindeutige Zeichenfolge im Konstruktor für die Klasse generieren und diese Zeichenfolge bei jedem Zugriff auf die Eigenschaft zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1417c-110">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> property by generating a unique string in the constructor for the class and returning that string whenever the property is accessed.</span></span>  
  
3. <span data-ttu-id="1417c-111">Implementieren Sie die schreibgeschützte <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A>-Eigenschaft, indem Sie einen <xref:System.IdentityModel.Claims.ClaimSet> zurückgeben, der den Richtlinienaussteller darstellt.</span><span class="sxs-lookup"><span data-stu-id="1417c-111">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> property by returning a <xref:System.IdentityModel.Claims.ClaimSet> that represents the policy issuer.</span></span> <span data-ttu-id="1417c-112">Dies könnte ein `ClaimSet` sein, der die Anwendung darstellt oder einen integrierten `ClaimSet` (z. B. den `ClaimSet`, der von der statischen <xref:System.IdentityModel.Claims.ClaimSet.System%2A>-Eigenschaft zurückgegeben wurde).</span><span class="sxs-lookup"><span data-stu-id="1417c-112">This could be a `ClaimSet` that represents the application or a built-in `ClaimSet` (for example, the `ClaimSet` returned by the static <xref:System.IdentityModel.Claims.ClaimSet.System%2A> property.</span></span>  
  
4. <span data-ttu-id="1417c-113">Implementieren Sie die <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>-Methode, wie in der folgenden Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1417c-113">Implement the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method as described in the following procedure.</span></span>  
  
### <a name="to-implement-the-evaluate-method"></a><span data-ttu-id="1417c-114">So implementieren Sie die Evaluate-Methode</span><span class="sxs-lookup"><span data-stu-id="1417c-114">To implement the Evaluate method</span></span>  
  
1. <span data-ttu-id="1417c-115">Zwei Parameter werden an diese Methode übergeben: eine Instanz der <xref:System.IdentityModel.Policy.EvaluationContext>-Klasse und ein Objektverweis.</span><span class="sxs-lookup"><span data-stu-id="1417c-115">Two parameters are passed to this method: an instance of the <xref:System.IdentityModel.Policy.EvaluationContext> class and an object reference.</span></span>  
  
2. <span data-ttu-id="1417c-116">Wenn die benutzerdefinierte Autorisierungs Richtlinie- <xref:System.IdentityModel.Claims.ClaimSet> Instanzen ohne Berücksichtigung des aktuellen Inhalts von hinzufügt <xref:System.IdentityModel.Policy.EvaluationContext> , fügen Sie jedes hinzu, `ClaimSet` indem Sie die <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> -Methode aufrufen und `true` von der-Methode zurückgeben <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> .</span><span class="sxs-lookup"><span data-stu-id="1417c-116">If the custom authorization policy adds <xref:System.IdentityModel.Claims.ClaimSet> instances without regard to the current content of the <xref:System.IdentityModel.Policy.EvaluationContext>, then add each `ClaimSet` by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and return `true` from the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method.</span></span> <span data-ttu-id="1417c-117">Die Rückgabe von `true` zeigt der Autorisierungsinfrastruktur an, dass die Autorisierungsrichtlinie ihre Funktion erfüllt hat und nicht erneut aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="1417c-117">Returning `true` indicates to the authorization infrastructure that the authorization policy has performed its work and does not need to be called again.</span></span>  
  
3. <span data-ttu-id="1417c-118">Wenn die benutzerdefinierte Autorisierungsrichtlinie Sätze von Ansprüchen nur hinzufügt, wenn bestimmte Ansprüche bereits im `EvaluationContext` vorhanden sind, suchen Sie diese Ansprüche, indem Sie die `ClaimSet`-Instanzen, die von der <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>-Eigenschaft zurückgegeben werden, analysieren.</span><span class="sxs-lookup"><span data-stu-id="1417c-118">If the custom authorization policy adds claim sets only if certain claims are already present in the `EvaluationContext`, then look for those claims by examining the `ClaimSet` instances returned by the <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> property.</span></span> <span data-ttu-id="1417c-119">Wenn die Ansprüche vorhanden sind, fügen Sie den neuen Satz von Ansprüchen hinzu, indem Sie die <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29>-Methode aufrufen, und geben Sie `true` zurück, wenn keine weiteren Sätze von Ansprüchen hinzugefügt werden müssen. Dies zeigt der Autorisierungsinfrastruktur an, dass die Autorisierungsrichtlinie ihre Funktion erfüllt hat.</span><span class="sxs-lookup"><span data-stu-id="1417c-119">If the claims are present, then add the new claim sets by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and, if no more claim sets are to be added, return `true`, indicating to the authorization infrastructure that the authorization policy has completed its work.</span></span> <span data-ttu-id="1417c-120">Wenn die Ansprüche nicht vorhanden sind, geben Sie `false` zurück. Dies gibt an, dass die Autorisierungsrichtlinie erneut aufgerufen werden muss, wenn andere Autorisierungsrichtlinien dem `EvaluationContext` weitere Sätze von Ansprüchen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1417c-120">If the claims are not present, return `false`, indicating that the authorization policy should be called again if other authorization policies add more claim sets to the `EvaluationContext`.</span></span>  
  
4. <span data-ttu-id="1417c-121">In komplexeren Verarbeitungsszenarien wird der zweite Parameter der <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>-Methode zum Speichern einer Zustandsvariablen verwendet, die von der Autorisierungsinfrastruktur bei jedem nachfolgenden Aufruf der <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>-Methode für eine bestimmte Auswertung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1417c-121">In more complex processing scenarios, the second parameter of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method is used to store a state variable that the authorization infrastructure will pass back during each subsequent call to the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method for a particular evaluation.</span></span>  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a><span data-ttu-id="1417c-122">So geben Sie eine benutzerdefinierte Autorisierungsrichtlinie durch Konfiguration an</span><span class="sxs-lookup"><span data-stu-id="1417c-122">To specify a custom authorization policy through configuration</span></span>  
  
1. <span data-ttu-id="1417c-123">Geben Sie den Typ der benutzerdefinierten Autorisierungsrichtlinie im `policyType`-Attribut des `add`-Elements und des `authorizationPolicies`-Elements des `serviceAuthorization`-Elements an.</span><span class="sxs-lookup"><span data-stu-id="1417c-123">Specify the type of the custom authorization policy in the `policyType` attribute in the `add` element in the `authorizationPolicies` element in the `serviceAuthorization` element.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>  
            <add policyType="Samples.MyAuthorizationPolicy" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a><span data-ttu-id="1417c-124">So geben Sie eine benutzerdefinierte Autorisierungsrichtlinie durch Code an</span><span class="sxs-lookup"><span data-stu-id="1417c-124">To specify a custom authorization policy through code</span></span>  
  
1. <span data-ttu-id="1417c-125">Erstellen Sie eine <xref:System.Collections.Generic.List%601> von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1417c-125">Create a <xref:System.Collections.Generic.List%601> of <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2. <span data-ttu-id="1417c-126">Erstellen Sie eine Instanz der benutzerdefinierten Autorisierungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="1417c-126">Create an instance of the custom authorization policy.</span></span>  
  
3. <span data-ttu-id="1417c-127">Fügen Sie der Liste die Autorisierungsrichtlinieninstanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="1417c-127">Add the authorization policy instance to the list.</span></span>  
  
4. <span data-ttu-id="1417c-128">Wiederholen Sie die Schritte 2 und 3 für jede benutzerdefinierte Autorisierungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="1417c-128">Repeat steps 2 and 3 for each custom authorization policy.</span></span>  
  
5. <span data-ttu-id="1417c-129">Weisen Sie der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>-Eigenschaft eine schreibgeschützte Version der Liste zu.</span><span class="sxs-lookup"><span data-stu-id="1417c-129">Assign a read-only version of the list to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> property.</span></span>  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1417c-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1417c-130">Example</span></span>  

 <span data-ttu-id="1417c-131">Im folgenden Beispiel wird eine vollständige Implementierung der <xref:System.IdentityModel.Policy.IAuthorizationPolicy> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1417c-131">The following example shows a complete <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementation.</span></span>  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1417c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1417c-132">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="1417c-133">Vorgehensweise: Vergleichen von Ansprüchen</span><span class="sxs-lookup"><span data-stu-id="1417c-133">How to: Compare Claims</span></span>](how-to-compare-claims.md)
- [<span data-ttu-id="1417c-134">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="1417c-134">How to: Create a Custom Authorization Manager for a Service</span></span>](how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="1417c-135">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1417c-135">Authorization Policy</span></span>](../samples/authorization-policy.md)
