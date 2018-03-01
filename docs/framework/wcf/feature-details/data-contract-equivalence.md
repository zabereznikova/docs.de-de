---
title: "Datenvertragsäquivalenz"
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
- data contracts [WCF], equivalence
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4059fa401d082f4408080cf5fd13f1331314a2d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="data-contract-equivalence"></a>Datenvertragsäquivalenz
Damit ein Client erfolgreich Daten eines bestimmten Typs an einen Dienst sendet oder ein Dienst erfolgreich Daten an einen Client sendet, muss der gesendete Typ nicht unbedingt an der Empfängerseite vorhanden sein. Die einzige Anforderung ist, dass die Datenverträge beider Typen äquivalent sind. (Manchmal strenger Äquivalenz ist nicht erforderlich, wie in beschrieben [Datenvertragsversionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).)  
  
 Die Äquivalenz von Datenverträgen wird durch denselben Namespace und Namen gewährleistet. Darüber hinaus muss jeder Datenmember auf einer Seite über einen entsprechenden Datenmember auf der anderen Seite verfügen.  
  
 Die Äquivalenz von Datenmembern wird durch denselben Namen gewährleistet. Darüber hinaus müssen sie denselben Datentyp aufweisen; das heißt, ihre Datenverträge müssen äquivalent sein.  
  
> [!NOTE]
>  Bei Datenvertragsnamen und Namespaces sowie Datenmembernamen ist Groß-/Kleinschreibung zu beachten.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Datenvertragsnamen und Namespaces sowie Datenmembernamen finden Sie unter [Datenvertragsnamen](../../../../docs/framework/wcf/feature-details/data-contract-names.md).  
  
 Sind zwei Typen auf derselben Seite vorhanden (Absender oder Empfänger) und sind die Datenverträge nicht äquivalent (wenn sie beispielsweise unterschiedliche Datenmember besitzen), sollten sie nicht denselben Name und denselben Namespace erhalten. Falls Sie doch denselben Namen bzw. Namespace zuweisen, werden möglicherweise Ausnahmen ausgelöst.  
  
 Die Datenverträge für die folgenden Typen sind äquivalent:  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## <a name="data-member-order-and-data-contract-equivalence"></a>Datenmemberreihenfolge und Datenvertragsäquivalenz  
 Die Verwendung der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>-Klasse wirkt sich unter Umständen auf die Äquivalenz des Datenvertrags aus. Die Datenverträge sind nur äquivalent, wenn sie über Member verfügen, die in der gleichen Reihenfolge angezeigt werden. Die Standardreihenfolge ist alphabetisch. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Datenmemberreihenfolge](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 Zum Beispiel führt der folgende Code zu äquivalenten Datenverträgen.  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 Folgendes führt jedoch nicht zu einem äquivalenten Datenvertrag.  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## <a name="inheritance-interfaces-and-data-contract-equivalence"></a>Vererbung, Schnittstellen und Datenvertragsäquivalenz  
 Beim Bestimmen der Äquivalenz wird ein Datenvertrag, der von einem anderen Datenvertrag erbt, so behandelt, als ob es sich nur um einen Datenvertrag mit allen Datenmembern vom Basistyp handelt. Die Reihenfolge der Datenmember muss übereinstimmen, und die Basistypmember müssen in der Reihenfolge vor den abgeleiteten Typmembern stehen. Verfügen zwei Datenmember &#8211; wie im folgenden Codesbeispiel &#8211; über denselben Reihenfolgenwert, werden diese Datenmember darüber hinaus alphabetisch sortiert. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Datenmemberreihenfolge](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 Im folgenden Beispiel entspricht der Datenvertrag für den Typ `Employee` dem Datenvertrag für den Typ `Worker`.  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 Beim Übergeben von Parametern und der Rückgabe von Werten zwischen einem Client und einem Dienst kann ein Datenvertrag von einer Basisklasse nicht gesendet werden, wenn der empfangende Endpunkt einen Datenvertrag von einer abgeleiteten Klasse erwartet. Dies stimmt mit objektorientierten Programmierungsgrundsätzen überein. Im vorherigen Beispiel, ein Objekt des Typs `Person` kann nicht gesendet werden, wenn ein `Employee` wird erwartet.  
  
 Ein Datenvertrag von einer abgeleiteten Klasse kann gesendet werden, wenn ein Datenvertrag von einer Basisklasse erwartet wird. Dies ist jedoch nur möglich, falls der empfangende Endpunkt unter Verwendung von <xref:System.Runtime.Serialization.KnownTypeAttribute> über den abgeleiteten Typen "informiert" ist. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Bekannte Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md). Im vorangegangenen Beispiel kann ein Objekt vom Typ `Employee` gesendet werden, wenn eine `Person` erwartet wird. Dies ist jedoch nur möglich, falls der Empfängercode <xref:System.Runtime.Serialization.KnownTypeAttribute> verwendet, um es in die Liste der bekannten Typen aufzunehmen.  
  
 Beim Übergeben von Parametern und Rückgabewerten zwischen Anwendungen entspricht der erwartete Typ (sofern es sich dabei um eine Schnittstelle handelt) dem erwarteten Typ <xref:System.Object>. Da jeder Typ letztlich von <xref:System.Object> abgeleitet wird, wird jeder Datenvertrag letztlich vom Datenvertrag für <xref:System.Object> abgeleitet. So kann jeder Datenvertragstyp übergeben werden, wenn eine Schnittstelle erwartet wird. Zusätzliche Schritte sind erforderlich, um erfolgreich arbeiten mit Schnittstellen; Weitere Informationen finden Sie unter [Datenvertragstypen bezeichnet](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Datenmemberreihenfolge](../../../../docs/framework/wcf/feature-details/data-member-order.md)  
 [Bekannte Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Datenvertragsnamen](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
