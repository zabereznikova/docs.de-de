---
title: Generische Typen und Reflektion (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cea1f48f336e4c73fa317d1cbbab3d06ceb6045f
ms.lasthandoff: 03/13/2017

---
# <a name="generics-and-reflection-c-programming-guide"></a>Generische Typen und Reflektion (C#-Programmierhandbuch)
Da die Common Language Runtime (CLR) Zugriff auf generische Typinformationen zur Laufzeit verfügt, können Sie die Reflektion zum Abrufen von Informationen über generische Typen genauso wie für nicht generische Typen verwenden. Weitere Informationen finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 In [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] wurden mehrere neue Member zur <xref:System.Type>-Klasse hinzugefügt, um Laufzeitinformationen für generische Typen zu ermöglichen. Weitere Informationen zur Verwendung dieser Methoden und Eigenschaften finden Sie in der Dokumentation zu diesen Klassen. Der Namespace <xref:System.Reflection.Emit> enthält auch neue Member, die generische Typen unterstützen. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe](http://msdn.microsoft.com/library/07d5f01a-7b5b-40ea-9b15-f21561098fe4).  
  
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
  
 Außerdem wurden neue Member zur <xref:System.Reflection.MethodInfo>-Klasse hinzugefügt, um Laufzeitinformationen für generische Methoden zu ermöglichen. Eine Liste der Liste der invarianten Bedingungen für Begriffe, für Begriffe, die für die Reflektion mit generischen Methoden verwendet werden, finden Sie in den Hinweisen zur Eigenschaft <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>.  
  
|System.Reflection.MemberInfo-Membername|Beschreibung|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|Gibt TRUE zurück, wenn eine Methode generisch ist|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Gibt ein Array von Type-Objekten zurück, die die Typargumente einer konstruierten generischen Methode oder die Typparameter einer generischen Methodendefinition darstellen|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Gibt die zugrunde liegende generische Methodendefinition für die aktuelle konstruierte Methode zurück|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Gibt TRUE zurück, wenn die Methode oder einer ihrer einschließenden Typen Typparameter enthält, für die keine bestimmten Typen angegeben wurden|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Gibt TRUE zurück, wenn der aktuelle <xref:System.Reflection.MethodInfo>-Member die Definition einer generischen Methode darstellt|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Ersetzt die Typparameter der aktuellen generischen Methodendefinition durch die Elemente eines Arrays von Typen und gibt ein <xref:System.Reflection.MethodInfo>-Objekt zurück, das die sich ergebende konstruierte Methode darstellt.|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Reflektion und generische Typen](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)   
 [Generika](https://msdn.microsoft.com/library/ms172192)
