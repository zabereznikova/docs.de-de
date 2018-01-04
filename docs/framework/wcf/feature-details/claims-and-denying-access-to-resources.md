---
title: "Ansprüche und das Verweigern des Zugriffs auf Ressourcen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156856ddd1a4c3b1d8f77a8a61f7e0336f993839
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="claims-and-denying-access-to-resources"></a>Ansprüche und das Verweigern des Zugriffs auf Ressourcen
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützt einen anspruchsbasierten Autorisierungsmechanismus. Systeme erlauben den Zugriff auf Ressourcen basierend auf dem Vorhandensein von Ansprüchen, verweigern jedoch auch häufig einen solchen Zugriff. Derartige Systeme sollten den <xref:System.IdentityModel.Policy.AuthorizationContext> nach Ansprüchen untersuchen, die dazu führen, dass der Zugriff verweigert wird, bevor sie nach Ansprüchen suchen, die zum Zulassen des Zugriffs führen.  
  
 Ein System kann beispielsweise einem Benutzer, der einen Anspruch des Typs `Age`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und den Ressourcenwert `Under 21` besitzt, den Zugriff auf eine Ressource nur verweigern, wenn dieser außerdem einen Anspruch des Typs `Name`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.Identity%2A> und den Ressourcenwert `Mallory` besitzt. Anders ausgedrückt, das System verweigert jedem Benutzer den Zugriff, der unter 21 Jahre alt ist, und lässt den Zugriff zu, wenn der Name Mallory lautet. Um diese semantischen Informationen richtig zu implementieren, ist es wichtig, erst nach dem `Age`-Anspruch zu suchen und dann zu bestimmen, ob das Alter unter 21 Jahre liegt. Andernfalls kann, wenn Mallory unter 21 ist, der Zugriff auf die Ressource einzig auf Basis des `Name`-Anspruchs zugelassen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Ansprüche und Token](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
