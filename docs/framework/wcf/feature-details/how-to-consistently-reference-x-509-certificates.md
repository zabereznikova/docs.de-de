---
title: 'Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2cc313be8c3d6325630e57e0b0e845ad4902bd2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate
Sie haben verschiedene Möglichkeiten, Zertifikate anzugeben: anhand des Hashwerts des Zertifikats, anhand des Ausstellers und der Seriennummer oder anhand der Schlüsselkennung des Antragstellers (Subject Key Identifier, SKI). Die Schlüsselkennung des Antragstellers gibt den öffentlichen Schlüssel des Zertifikatantagstellers eindeutig an. Sie wird häufig für digitale XML-Signaturen verwendet. Der SKI-Wert wird in der Regel Bestandteil des x. 509-Zertifikats als ein *x. 509-zertifikatserweiterung*. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]verfügt über einen standardmäßigen *verweisstil* , den Aussteller und die Seriennummer verwendet, wenn die SKI-Erweiterung das Zertifikat nicht vorhanden ist. Enthält das Zertifikat die SKI-Erweiterung, verwendet der Standardverweis die Schlüsselkennung des Antragstellers, um auf das Zertifikat zu verweisen. Wenn Sie während der Entwicklung einer Anwendung von Zertifikaten, die die SKI-Erweiterung nicht verwenden, auf Zertifikate umstellen, die die SKI-Erweiterung verwenden, ändert sich auch der Verweisstil in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-generierten Nachrichten.  
  
 Wenn unabhängig vom Vorhandensein einer SKI-Erweiterung ein einheitlicher Verweisstil erforderlich ist, kann der gewünschte Verweisstil wie im folgenden Code dargestellt konfiguriert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein benutzerdefiniertes Sicherheitsbindungselement erstellt, das einen einzigen einheitlichen Verweisstil, den Namen des Ausstellers und die Seriennummer verwendet.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
