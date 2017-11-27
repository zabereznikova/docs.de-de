---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die SymmetricSecurityBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die SymmetricSecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Reihenfolge der Nachrichtenverschlüsselung und -signatur für diese Bindung.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Bindung eine Signaturbestätigung erfordert.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
