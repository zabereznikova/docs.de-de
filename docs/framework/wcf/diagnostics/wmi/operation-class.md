---
title: Operation-Klasse
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165073"
---
# <a name="operation-class"></a>Operation-Klasse
Vorgang  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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
  
 Gibt an, dass ein Vorgang asynchron implementiert wird eine `Begin`[spitze Klammern öffnen/schließen] und `End`[Winkelklammern öffnen/schließen]-Methodenpaar in einem Dienstvertrag.  
  
### <a name="behaviors"></a>Verhalten  
 Datentyp: Behavior-array  
  
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
  
### <a name="name"></a>Name  
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

- <xref:System.ServiceModel.Description.OperationDescription>
