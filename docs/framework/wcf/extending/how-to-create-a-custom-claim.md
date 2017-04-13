---
title: "Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs
Die identitätsmodellinfrastruktur in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet eine Reihe von integrierten Anspruchstypen und-Rechte mit den Hilfsfunktionen zum Erstellen von <xref:System.IdentityModel.Claims.Claim> Instanzen mit diesen Typen und rechten. Diese integrierten Ansprüche sind so konzipiert, dass sie Informationen modellieren, die sich in von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standardmäßig unterstützten Clientanmeldeinformationstypen befinden. In vielen Fällen sind die integrierten Ansprüche ausreichend; für einige Anwendungen sind jedoch unter Umständen benutzerdefinierte Ansprüche erforderlich. Ein Anspruch besteht aus dem Anspruchstyp, der Ressource, für die der Anspruch gilt, und dem Recht, das über diese Ressource gewährt wird. In diesem Thema wird beschrieben, wie Sie einen benutzerdefinierten Anspruch erstellen.  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a>So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem primitiven Datentyp basiert  
  
1.  Erstellen eines benutzerdefinierten Anspruchs durch Übergeben der Anspruchstyp, Ressourcenwert und rechts, um die <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> Konstruktor.  
  
    1.  Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.  
  
         Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner. Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist. Eine Liste der Anspruchstypen, die durch definiert sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], finden Sie unter der <xref:System.IdentityModel.Claims.ClaimTypes> Klasse.  
  
    2.  Wählen Sie den primitiven Datentyp und den Wert für die Ressource aus.  
  
         Eine Ressource ist ein Objekt. Der CLR-Typ der Ressource kann Primitiv sein, wie z. B. <xref:System.String> oder <xref:System.Int32>, oder einen beliebigen serialisierbaren Typ. Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] an verschiedenen Punkten serialisiert werden. Primitive Typen sind serialisierbar.  
  
    3.  Wählen Sie ein von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definiertes Recht oder einen eindeutigen Wert für ein benutzerdefiniertes Recht aus.  
  
         Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner. Die Rechte, die durch definiert sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden gemäß der <xref:System.IdentityModel.Claims.Rights> Klasse.  
  
         Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.  
  
         Das folgende Codebeispiel erstellt einen benutzerdefinierten Anspruch mit einem Anspruchstyp `http://example.org/claims/simplecustomclaim`, für eine Ressource mit dem Namen `Driver's License`, und klicken Sie mit der <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> rechts.  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a>So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem nicht primitiven Datentyp basiert  
  
1.  Erstellen eines benutzerdefinierten Anspruchs durch Übergeben der Anspruchstyp, Ressourcenwert und rechts, um die <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> Konstruktor.  
  
    1.  Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.  
  
         Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner. Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist. Eine Liste der Anspruchstypen, die durch definiert sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], finden Sie unter der <xref:System.IdentityModel.Claims.ClaimTypes> Klasse.  
  
    2.  Wählen oder definieren Sie einen serialisierbaren nicht primitiven Typ für die Ressource.  
  
         Eine Ressource ist ein Objekt. Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] an verschiedenen Punkten serialisiert werden. Primitive Typen sind bereits serialisierbar.  
  
         Wenn ein neuer Typ definiert ist, gelten die <xref:System.Runtime.Serialization.DataContractAttribute> der-Klasse. Auch die <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut auf alle Member des neuen Typs, die als Teil des Anspruchs serialisiert werden müssen.  
  
         Im folgenden Codebeispiel wird ein benutzerdefinierter Ressourcetyp mit der Bezeichnung `MyResourceType` definiert.  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]  
  
    3.  Wählen Sie ein von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definiertes Recht oder einen eindeutigen Wert für ein benutzerdefiniertes Recht aus.  
  
         Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner. Die Rechte, die durch definiert sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden gemäß der <xref:System.IdentityModel.Claims.Rights> Klasse.  
  
         Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.  
  
         Das folgende Codebeispiel erstellt einen benutzerdefinierten Anspruch mit einem Anspruchstyp `http://example.org/claims/complexcustomclaim`, einem benutzerdefinierten Ressourcentyp `MyResourceType`, und mit der <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> rechten.  
  
     [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
     [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie ein benutzerdefinierter Anspruch mit einem primitiven Ressourcentyp und ein benutzerdefinierter Anspruch mit einem nicht primitiven Ressourcentyp erstellt wird.  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Claims.Claim>   
 <xref:System.IdentityModel.Claims.Rights>   
 <xref:System.IdentityModel.Claims.ClaimTypes>   
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)   
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)