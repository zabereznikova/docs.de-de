---
title: Generics und Reflektion – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Verwendung der Reflexion zum Abrufen von Informationen zu generischen Typen. Sehen Sie sich eine Liste der Nutzungsbedingungen für die Reflexion generischer Typen an.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
ms.openlocfilehash: 5439412231ab1bf9ed523d6786af67984ab2d0c3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172969"
---
# <a name="generics-and-reflection-c-programming-guide"></a>Generics und Reflektion (C#-Programmierhandbuch)

Da die Common Language Runtime (CLR) Zugriff auf generische Typinformationen zur Laufzeit verfügt, können Sie die Reflektion zum Abrufen von Informationen über generische Typen genauso wie für nicht generische Typen verwenden. Weitere Informationen finden Sie unter [Generics zur Laufzeit](./generics-in-the-run-time.md).  
  
 In .NET Framework 2.0 wurden mehrere neue Member zur <xref:System.Type>-Klasse hinzugefügt, um Laufzeitinformationen für generische Typen zu ermöglichen. Weitere Informationen zur Verwendung dieser Methoden und Eigenschaften finden Sie in der Dokumentation zu diesen Klassen. Der <xref:System.Reflection.Emit>-Namespace enthält auch neue Member, die Generics unterstützen. Weitere Informationen finden Sie unter [How to: Definieren eines generischen Typs mit Reflektionsausgabe](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).  
  
 Eine Liste der invarianten Bedingungen für Begriffe, für Begriffe, die für die Reflektion mit generischen Methoden verwendet werden, finden Sie in den Hinweisen zur Eigenschaft <xref:System.Type.IsGenericType%2A>.  
  
|System.Type-Membername|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|Gibt TRUE zurück, wenn ein Typ generisch ist|  
|<xref:System.Type.GetGenericArguments%2A>|Gibt ein Array von `Type`-Objekten zurück, die die bereitgestellten Typargumente für einen konstruierten Typ oder die Typparameter einer generischen Typdefinition darstellen|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Gibt die zugrunde liegende generische Typdefinition für den aktuellen konstruierten Typ zurück|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Gibt ein Array von `Type`-Objekten zurück, die die Einschränkungen für den aktuellen generischen Typparameter darstellen.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Gibt TRUE zurück, wenn der Typ oder einer seiner einschließenden Typen oder Methoden Typparameter enthalten, für die keine bestimmten Typen angegeben wurden|  
|<xref:System.Type.GenericParameterAttributes%2A>|Ruft eine Kombination von `GenericParameterAttributes`-Flags ab, die die speziellen Einschränkungen des aktuellen generischen Typparameters beschreiben|  
|<xref:System.Type.GenericParameterPosition%2A>|Ruft für ein `Type`-Objekt, das einen Typparameter darstellt, die Position des Typparameters in der Typparameterliste des generischen Typs oder der generischen Methode, die den Typparameter deklariert|  
|<xref:System.Type.IsGenericParameter%2A>|Ruft einen Wert ab, der angibt, ob der aktuelle `Type` einen Typparameter einer generischen Typ- oder Methodendefinition darstellt|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Ruft einen Wert ab, der angibt, ob der aktuelle <xref:System.Type> eine generische Typdefinition darstellt, aus der andere generische Typen konstruiert werden können. Gibt TRUE zurück, wenn der Typ die Definition eines generischen Typs darstellt|  
|<xref:System.Type.DeclaringMethod%2A>|Gibt die generische Methode, die den aktuellen generischen Typparameter definiert, oder null zurück, wenn der Typparameter nicht von einer generischen Methode definiert wurde|  
|<xref:System.Type.MakeGenericType%2A>|Ersetzt die Typparameter der aktuellen generischen Typdefinition durch die Elemente eines Arrays von Typen und gibt ein <xref:System.Type>-Objekt zurück, das den resultierenden konstruierten Typ darstellt.|  
  
 Zusätzlich ermöglichen neue Member der <xref:System.Reflection.MethodInfo>-Klasse Laufzeitinformationen für generische Methoden. Eine Liste der invarianten Bedingungen für Begriffe, die für die Reflektion mit generischen Methoden verwendet werden, finden Sie unter den Hinweisen zur Eigenschaft <xref:System.Reflection.MethodBase.IsGenericMethod%2A>.  
  
|System.Reflection.MemberInfo-Membername|Beschreibung|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodBase.IsGenericMethod%2A>|Gibt TRUE zurück, wenn eine Methode generisch ist|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Gibt ein Array von Type-Objekten zurück, die die Typargumente einer konstruierten generischen Methode oder die Typparameter einer generischen Methodendefinition darstellen|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Gibt die zugrunde liegende generische Methodendefinition für die aktuelle konstruierte Methode zurück|  
|<xref:System.Reflection.MethodBase.ContainsGenericParameters%2A>|Gibt TRUE zurück, wenn die Methode oder einer ihrer einschließenden Typen Typparameter enthält, für die keine bestimmten Typen angegeben wurden|  
|<xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A>|Gibt TRUE zurück, wenn die aktuelle <xref:System.Reflection.MethodInfo> die Definition eines generischen Typs darstellt|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Ersetzt die Typparameter der aktuellen generischen Methodendefinition durch die Elemente eines Arrays von Typen und gibt ein <xref:System.Reflection.MethodInfo>-Objekt zurück, das die sich ergebende konstruierte Methode darstellt.|  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Generics](./index.md)
- [Reflektion und generische Typen](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- [Generics](../../../standard/generics/index.md)
