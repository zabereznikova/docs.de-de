---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 1c1c1e050cfef36aa53b83a764c0b7e308783394
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619608"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="f64a8-102">Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs</span><span class="sxs-lookup"><span data-stu-id="f64a8-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="f64a8-103">Die identitätsmodellinfrastruktur in Windows Communication Foundation (WCF) bietet eine Reihe von integrierten Anspruchstypen und-Rechte mit den Hilfsfunktionen zum Erstellen von <xref:System.IdentityModel.Claims.Claim> -Instanzen mit diesen Typen und rechten.</span><span class="sxs-lookup"><span data-stu-id="f64a8-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="f64a8-104">Diese integrierten Ansprüche sind Informationen zum Modell finden Sie in Typen von Clientanmeldeinformationen, die weiterhin WCF unterstützt standardmäßig soll.</span><span class="sxs-lookup"><span data-stu-id="f64a8-104">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="f64a8-105">In vielen Fällen sind die integrierten Ansprüche ausreichend; für einige Anwendungen sind jedoch unter Umständen benutzerdefinierte Ansprüche erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f64a8-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="f64a8-106">Ein Anspruch besteht aus dem Anspruchstyp, der Ressource, für die der Anspruch gilt, und dem Recht, das über diese Ressource gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="f64a8-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="f64a8-107">In diesem Thema wird beschrieben, wie Sie einen benutzerdefinierten Anspruch erstellen.</span><span class="sxs-lookup"><span data-stu-id="f64a8-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="f64a8-108">So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem primitiven Datentyp basiert</span><span class="sxs-lookup"><span data-stu-id="f64a8-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="f64a8-109">Erstellen Sie einen benutzerdefinierten Anspruch, indem Sie den Anspruchstyp, den Ressourcenwert und das Recht dem <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="f64a8-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="f64a8-110">Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.</span><span class="sxs-lookup"><span data-stu-id="f64a8-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="f64a8-111">Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f64a8-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="f64a8-112">Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="f64a8-113">Eine Liste der Anspruchstypen, die von WCF definiert sind, finden Sie unter den <xref:System.IdentityModel.Claims.ClaimTypes> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f64a8-113">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="f64a8-114">Wählen Sie den primitiven Datentyp und den Wert für die Ressource aus.</span><span class="sxs-lookup"><span data-stu-id="f64a8-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="f64a8-115">Eine Ressource ist ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="f64a8-115">A resource is an object.</span></span> <span data-ttu-id="f64a8-116">Der CLR-Typ der Ressource kann primitiv sein, z. B. <xref:System.String> oder <xref:System.Int32>, oder ein beliebiger serialisierbarer Typ.</span><span class="sxs-lookup"><span data-stu-id="f64a8-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="f64a8-117">Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche von WCF an verschiedenen Punkten serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f64a8-117">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="f64a8-118">Primitive Typen sind serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="f64a8-118">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="f64a8-119">Wählen Sie ein Recht, die von WCF oder einen eindeutigen Wert für ein benutzerdefiniertes Recht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-119">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="f64a8-120">Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f64a8-120">A right is a unique string identifier.</span></span> <span data-ttu-id="f64a8-121">Die Rechte, die von WCF definiert sind, sind in definiert die <xref:System.IdentityModel.Claims.Rights> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f64a8-121">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="f64a8-122">Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="f64a8-123">Im folgenden Codebeispiel wird ein benutzerdefinierter Anspruch mit einem Anspruchstyp `http://example.org/claims/simplecustomclaim` für eine Ressource mit der Bezeichnung `Driver's License` und mit dem <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>-Recht erstellt.</span><span class="sxs-lookup"><span data-stu-id="f64a8-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="f64a8-124">So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem nicht primitiven Datentyp basiert</span><span class="sxs-lookup"><span data-stu-id="f64a8-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="f64a8-125">Erstellen Sie einen benutzerdefinierten Anspruch, indem Sie den Anspruchstyp, den Ressourcenwert und das Recht dem <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="f64a8-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="f64a8-126">Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.</span><span class="sxs-lookup"><span data-stu-id="f64a8-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="f64a8-127">Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f64a8-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="f64a8-128">Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="f64a8-129">Eine Liste der Anspruchstypen, die von WCF definiert sind, finden Sie unter den <xref:System.IdentityModel.Claims.ClaimTypes> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f64a8-129">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="f64a8-130">Wählen oder definieren Sie einen serialisierbaren nicht primitiven Typ für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="f64a8-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="f64a8-131">Eine Ressource ist ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="f64a8-131">A resource is an object.</span></span> <span data-ttu-id="f64a8-132">Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche von WCF an verschiedenen Punkten serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f64a8-132">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="f64a8-133">Primitive Typen sind bereits serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="f64a8-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="f64a8-134">Wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute> auf die Klasse an, wenn ein neuer Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f64a8-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="f64a8-135">Wenden Sie auch das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf alle Member des neuen Typs an, die als Teil des Anspruchs serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f64a8-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="f64a8-136">Im folgenden Codebeispiel wird ein benutzerdefinierter Ressourcetyp mit der Bezeichnung `MyResourceType` definiert.</span><span class="sxs-lookup"><span data-stu-id="f64a8-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3. <span data-ttu-id="f64a8-137">Wählen Sie ein Recht, die von WCF oder einen eindeutigen Wert für ein benutzerdefiniertes Recht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-137">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="f64a8-138">Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="f64a8-138">A right is a unique string identifier.</span></span> <span data-ttu-id="f64a8-139">Die Rechte, die von WCF definiert sind, sind in definiert die <xref:System.IdentityModel.Claims.Rights> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f64a8-139">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="f64a8-140">Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="f64a8-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="f64a8-141">Im folgenden Codebeispiel wird ein benutzerdefinierter Anspruch mit einem Anspruchstyp `http://example.org/claims/complexcustomclaim`, einem benutzerdefinierten Ressourcentyp `MyResourceType` und mit dem <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>-Recht erstellt.</span><span class="sxs-lookup"><span data-stu-id="f64a8-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="f64a8-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f64a8-142">Example</span></span>  
 <span data-ttu-id="f64a8-143">Das folgende Codebeispiel veranschaulicht, wie ein benutzerdefinierter Anspruch mit einem primitiven Ressourcentyp und ein benutzerdefinierter Anspruch mit einem nicht primitiven Ressourcentyp erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f64a8-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="f64a8-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f64a8-144">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="f64a8-145">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="f64a8-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
