---
title: Operation-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54566bc452baa2e02cef7d8d13d29fcd5864c95c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="operation-class"></a>Operation-Klasse
Vorgang  
  
## <a name="syntax"></a>Syntax  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Operation-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Operation-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="action"></a>Aktion  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die WS-Adressierungsaktion der Anforderungsnachricht.  
  
### <a name="asyncpattern"></a>AsyncPattern  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, dass ein Vorgang implementiert wird asynchron mit einem `Begin`[spitze Klammern öffnen/schließen] und `End`[Klammern öffnen/schließen]-Methodenpaar in einem Dienstvertrag.  
  
### <a name="behaviors"></a>Verhalten  
 Datentyp: Behavior-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die mit diesem Vorgang verknüpften Verhalten.  
  
### <a name="iscallback"></a>IsCallback  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 True, wenn der Vorgang ein Rückrufvorgang ist.  
  
### <a name="isinitiating"></a>IsInitiating  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann.  
  
### <a name="isoneway"></a>IsOneWay  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.  
  
### <a name="isterminating"></a>IsTerminating  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob ein Vorgang eine Antwortnachricht zurückgibt.  
  
### <a name="methodsignature"></a>MethodSignature  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Methodensignatur des Vorgangs.  
  
### <a name="name"></a>name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vorgangs.  
  
### <a name="parametertypes"></a>ParameterTypes  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Parametertypen des Vorgangs.  
  
### <a name="replyaction"></a>ReplyAction  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.  
  
### <a name="returntype"></a>ReturnType  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Rückgabetyp des Vorgangs.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.OperationDescription>
