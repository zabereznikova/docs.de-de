---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: e78f577e0fd3473575fab998e55616936212ebb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185616"
---
# <a name="how-to-create-a-custom-claim"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs
Die Identitätsmodellinfrastruktur in Windows Communication Foundation (WCF) stellt eine Reihe integrierter Anspruchstypen und -rechte mit den Hilfsfunktionen zum Erstellen <xref:System.IdentityModel.Claims.Claim> von Instanzen mit diesen Typen und Rechten bereit. Diese integrierten Ansprüche wurden entwickelt, um Informationen in Clientanmeldeinformationstypen zu modellieren, die WCF standardmäßig unterstützt. In vielen Fällen sind die integrierten Ansprüche ausreichend; für einige Anwendungen sind jedoch unter Umständen benutzerdefinierte Ansprüche erforderlich. Ein Anspruch besteht aus dem Anspruchstyp, der Ressource, für die der Anspruch gilt, und dem Recht, das über diese Ressource gewährt wird. In diesem Thema wird beschrieben, wie Sie einen benutzerdefinierten Anspruch erstellen.  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a>So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem primitiven Datentyp basiert  
  
1. Erstellen Sie einen benutzerdefinierten Anspruch, indem Sie den Anspruchstyp, den Ressourcenwert und das Recht dem <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>-Konstruktor übergeben.  
  
    1. Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.  
  
         Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner. Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist. Eine Liste der Anspruchstypen, die von <xref:System.IdentityModel.Claims.ClaimTypes> WCF definiert sind, finden Sie in der Klasse.  
  
    2. Wählen Sie den primitiven Datentyp und den Wert für die Ressource aus.  
  
         Eine Ressource ist ein Objekt. Der CLR-Typ der Ressource kann primitiv sein, z. B. <xref:System.String> oder <xref:System.Int32>, oder ein beliebiger serialisierbarer Typ. Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche an verschiedenen Stellen von WCF serialisiert werden. Primitive Typen sind serialisierbar.  
  
    3. Wählen Sie ein Recht, das durch WCF definiert ist, oder einen eindeutigen Wert für ein benutzerdefiniertes Recht.  
  
         Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner. Die von WCF definierten Rechte werden <xref:System.IdentityModel.Claims.Rights> in der Klasse definiert.  
  
         Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.  
  
         Im folgenden Codebeispiel wird ein benutzerdefinierter Anspruch mit einem Anspruchstyp `http://example.org/claims/simplecustomclaim` für eine Ressource mit der Bezeichnung `Driver's License` und mit dem <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>-Recht erstellt.  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a>So erstellen Sie einen benutzerdefinierten Anspruch, der auf einem nicht primitiven Datentyp basiert  
  
1. Erstellen Sie einen benutzerdefinierten Anspruch, indem Sie den Anspruchstyp, den Ressourcenwert und das Recht dem <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>-Konstruktor übergeben.  
  
    1. Legen Sie einen eindeutigen Wert für den Anspruchstyp fest.  
  
         Der Anspruchstyp ist ein eindeutiger Zeichenfolgenbezeichner. Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für den Anspruchstyp verwendete Zeichenfolgenbezeichner eindeutig ist. Eine Liste der Anspruchstypen, die von <xref:System.IdentityModel.Claims.ClaimTypes> WCF definiert sind, finden Sie in der Klasse.  
  
    2. Wählen oder definieren Sie einen serialisierbaren nicht primitiven Typ für die Ressource.  
  
         Eine Ressource ist ein Objekt. Der CLR-Typ der Ressource muss serialisierbar sein, da Ansprüche an verschiedenen Stellen von WCF serialisiert werden. Primitive Typen sind bereits serialisierbar.  
  
         Wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute> auf die Klasse an, wenn ein neuer Typ definiert wird. Wenden Sie auch das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf alle Member des neuen Typs an, die als Teil des Anspruchs serialisiert werden müssen.  
  
         Im folgenden Codebeispiel wird ein benutzerdefinierter Ressourcetyp mit der Bezeichnung `MyResourceType` definiert.  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. Wählen Sie ein Recht, das durch WCF definiert ist, oder einen eindeutigen Wert für ein benutzerdefiniertes Recht.  
  
         Ein Recht ist ein eindeutiger Zeichenfolgenbezeichner. Die von WCF definierten Rechte werden <xref:System.IdentityModel.Claims.Rights> in der Klasse definiert.  
  
         Der Ersteller des benutzerdefinierten Anspruchs ist dafür verantwortlich, dass der für das Recht verwendete Zeichenfolgenbezeichner eindeutig ist.  
  
         Im folgenden Codebeispiel wird ein benutzerdefinierter Anspruch mit einem Anspruchstyp `http://example.org/claims/complexcustomclaim`, einem benutzerdefinierten Ressourcentyp `MyResourceType` und mit dem <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>-Recht erstellt.  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie ein benutzerdefinierter Anspruch mit einem primitiven Ressourcentyp und ein benutzerdefinierter Anspruch mit einem nicht primitiven Ressourcentyp erstellt wird.  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
