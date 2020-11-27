---
title: Erstellen von Ansprüchen und Ressourcenwerte
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: c3f36d607d88b208753066dcbd4e9baa6a2590fa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295131"
---
# <a name="claim-creation-and-resource-values"></a>Erstellen von Ansprüchen und Ressourcenwerte

Die <xref:System.IdentityModel.Claims.Claim>-Klasse bietet mehrere Methoden zum Erstellen von Instanzen von integrierten Anspruchstypen. Von diesen Methoden führen die folgenden keine semantische Prüfung oder Formatüberprüfung für die angegebene Ressource aus:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (überprüft die Länge oder den Inhalt des Bytearrays nicht)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (überprüft die Länge oder den Inhalt des Bytearrays nicht)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 Gehen Sie beim Aufrufen der oben beschriebenen Methoden äußerst sorgfältig vor, um sicherzustellen, dass die übergebenen Ressourcenwerte das richtige Format aufweisen oder die richtigen Informationen enthalten (oder beides).  
  
 Die folgenden Methoden werden mit bestimmten Typen verwendet:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](managing-claims-and-authorization-with-the-identity-model.md)
