---
title: Operation-Klasse
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 6b47d933dc84813532398830c92c95210208a709
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269157"
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
  
### <a name="action"></a>Action  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die WS-Adressierungsaktion der Anforderungsnachricht.  
  
### <a name="asyncpattern"></a>AsyncPattern  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, dass ein Vorgang asynchron mithilfe `Begin` der Methoden Paare [öffnende/schließende spitzen Klammern] und `End` [öffnende/schließende spitze Klammern] in einem Dienstvertrag implementiert wird.  
  
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

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Methodensignatur des Vorgangs.  
  
### <a name="name"></a>Name  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Name des Vorgangs.  
  
### <a name="parametertypes"></a>ParameterTypes  

 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Parametertypen des Vorgangs.  
  
### <a name="replyaction"></a>ReplyAction  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs.  
  
### <a name="returntype"></a>ReturnType  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Rückgabetyp des Vorgangs.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.OperationDescription>
