---
title: Ansprüche und das Verweigern des Zugriffs auf Ressourcen
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: df35ea2f01f96b044763c696434e5ede39d6b4bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715750"
---
# <a name="claims-and-denying-access-to-resources"></a>Ansprüche und das Verweigern des Zugriffs auf Ressourcen
Windows Communication Foundation (WCF) unterstützt einen anspruchsbasierten Autorisierungsmechanismus. Systeme erlauben den Zugriff auf Ressourcen basierend auf dem Vorhandensein von Ansprüchen, verweigern jedoch auch häufig einen solchen Zugriff. Derartige Systeme sollten den <xref:System.IdentityModel.Policy.AuthorizationContext> nach Ansprüchen untersuchen, die dazu führen, dass der Zugriff verweigert wird, bevor sie nach Ansprüchen suchen, die zum Zulassen des Zugriffs führen.  
  
 Ein System kann beispielsweise einem Benutzer, der einen Anspruch des Typs `Age`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und den Ressourcenwert `Under 21` besitzt, den Zugriff auf eine Ressource nur verweigern, wenn dieser außerdem einen Anspruch des Typs `Name`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.Identity%2A> und den Ressourcenwert `Mallory` besitzt. Anders ausgedrückt, das System verweigert jedem Benutzer den Zugriff, der unter 21 Jahre alt ist, und lässt den Zugriff zu, wenn der Name Mallory lautet. Um diese semantischen Informationen richtig zu implementieren, ist es wichtig, erst nach dem `Age`-Anspruch zu suchen und dann zu bestimmen, ob das Alter unter 21 Jahre liegt. Andernfalls kann, wenn Mallory unter 21 ist, der Zugriff auf die Ressource einzig auf Basis des `Name`-Anspruchs zugelassen werden.  
  
## <a name="see-also"></a>Siehe auch
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Ansprüche und Token](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
