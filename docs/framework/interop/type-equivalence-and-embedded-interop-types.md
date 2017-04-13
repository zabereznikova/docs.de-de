---
title: "Type Equivalence and Embedded Interop Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "type equivalence"
  - "embedded interop types"
  - "primary interop assemblies,not necessary in CLR version 4"
  - "NoPIA"
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Type Equivalence and Embedded Interop Types
Ab der Version [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] unterstützt die Common Language Runtime das direkte Einbetten von Typinformationen für COM\-Typen in verwaltete Assemblys, anstatt zu fordern, dass die verwalteten Assemblys, Typinformationen für COM\-Typen aus Interopassemblys abrufen.  Da die eingebetteten Typinformationen nur die Typen und Member enthalten, die tatsächlich von einer verwalteten Assembly verwendet werden, können zwei verwaltete Assemblys über stark unterschiedliche Ansichten des gleichen COM\-Typs verfügen.  Jede verwaltete Assembly besitzt ein anderes <xref:System.Type>\-Objekt, um seine Ansicht des COM\-Typs darzustellen.  Die Common Language Runtime unterstützt Äquivalenz zwischen diesen unterschiedlichen Ansichten für Schnittstellen, Strukturen, Enumerationen und Delegaten.  
  
 Typäquivalenz bedeutet, dass ein COM\-Objekt, das von einer verwalteten Assembly an eine andere übergeben wird, in der empfangenden Assembly in den entsprechenden verwalteten Typ umgewandelt werden kann.  
  
> [!NOTE]
>  Typäquivalenz und eingebettete Interop\-Typen vereinfachen die Bereitstellung von Anwendungen und Add\-Ins, die COM\-Komponenten verwenden, da es nicht notwendig ist, Interopassemblys mit den Anwendungen bereitzustellen.  Entwickler von freigegebenen COM\-Komponenten müssen immer noch primäre Interopassemblys \(PIAs\) erstellen, wenn ihre Komponenten mit früheren Versionen von .NET Framework kompatibel sein sollen.  
  
## Typäquivalenz  
 Äquivalenz von COM\-Typen wird für Schnittstellen, Strukturen, Enumerationen und Delegaten unterstützt.  COM\-Typen gelten als Äquivalent, wenn alle der folgenden Bedingungen wahr sind:  
  
-   Die Typen sind beide Schnittstellen oder beide Strukturen oder beide Enumerationen oder beide Delegaten.  
  
-   Die Typen besitzen die gleiche Identität \(siehe nächster Abschnitt\).  
  
-   Beide Typen sind für Typäquivalenz geeignet \(siehe Abschnitt [Markieren von COM\-Typen für Typäquivalenz](#type_equiv)\).  
  
### Typidentität  
 Zwei Typen besitzen die gleiche Identität, wenn ihre Bereiche und Identitäten übereinstimmen, anders ausgedrückt, wenn sie jeweils über das <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>\-Attribut verfügen, und wenn die zwei Attribute die folgenden übereinstimmenden Eigenschaften besitzen: <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> und <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>.  Beim Vergleich für <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> wird die Groß\- und Kleinschreibung nicht berücksichtigt.  
  
 Wenn ein Typ nicht über das <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>\-Attribut verfügt, oder wenn es ein <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>\-Attribut besitzt, durch das kein Bereich und Bezeichner angegeben wird, kann der Typ immer noch folgendermaßen für Äquivalenz in Betracht gezogen werden:  
  
-   Für Schnittstellen wird der Wert des <xref:System.Runtime.InteropServices.GuidAttribute>\-Objekts anstelle der <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=fullName>\-Eigenschaft verwendet, und die <xref:System.Type.FullName%2A?displayProperty=fullName>\-Eigenschaft \(das heißt, der Typname, einschließlich des Namespaces\) wird anstelle der <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=fullName>\-Eigenschaft verwendet.  
  
-   Für Strukturen, Enumerationen und Delegaten wird das <xref:System.Runtime.InteropServices.GuidAttribute>\-Objekt der enthaltenden Assembly anstelle der <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A>\-Eigenschaft verwendet, und die <xref:System.Type.FullName%2A?displayProperty=fullName>\-Eigenschaft wird anstelle der <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>\-Eigenschaft verwendet.  
  
<a name="type_equiv"></a>   
### Markieren von COM\-Typen für Typäquivalenz  
 Sie können einen Typ für Typäquivalenz auf zweierlei Art als geeignet markieren:  
  
-   Übernehmen Sie das <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>\-Attribut für den Typ.  
  
-   Legen Sie den Typ als COM\-Importtyp fest.  Eine Schnittstelle ist ein COM\-Importtyp, wenn sie über das <xref:System.Runtime.InteropServices.ComImportAttribute>\-Attribut verfügt.  Eine Schnittstelle, Struktur, Enumeration oder ein Delegat ist ein COM\-Importtyp, wenn die Assembly, in der der Typ definiert wird, über das <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>\-Attribut verfügt.  
  
## Siehe auch  
 <xref:System.Type.IsEquivalentTo%2A>   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/de-de/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)