---
title: "Generische Typen und Reflektion (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Generika [C#], Reflektion"
  - "Reflektion [C#], Generische Typen"
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Generische Typen und Reflektion (C#-Programmierhandbuch)
Weil die Common Language Runtime \(CLR\) zur Laufzeit Zugriff auf generische Typinformationen hat, können Sie mithilfe von Reflektion Informationen über generische Typen genauso wie für nicht generische Typen erhalten.  Weitere Informationen finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 In [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] werden der <xref:System.Type>\-Klasse mehrere neue Member hinzugefügt, um Laufzeitinformationen für generische Typen zu ermöglichen.  Weitere Informationen zur Verwendung dieser Methoden und Eigenschaften finden Sie in der Dokumentation zu diesen Klassen. Der <xref:System.Reflection.Emit>\-Namespace enthält auch neue Member, die Generika unterstützen.  Weitere Informationen finden Sie unter [Gewusst wie: Definieren eines generischen Typs mit Reflektionsausgabe](../Topic/How%20to:%20Define%20a%20Generic%20Type%20with%20Reflection%20Emit.md).  
  
 Eine Liste der unveränderlichen Bedingungen für allgemeine Begriffe, die in generischer Reflektion verwendet werden, finden Sie in den Hinweisen zur <xref:System.Type.IsGenericType%2A>\-Eigenschaft.  
  
|System.Type\-Membername|Beschreibung|  
|-----------------------------|------------------|  
|<xref:System.Type.IsGenericType%2A>|Gibt true zurück, wenn ein Typ generisch ist.|  
|<xref:System.Type.GetGenericArguments%2A>|Gibt ein Array von `Type`\-Objekten zurück, die die für einen konstruierten Typ bereitgestellten Typargumente oder die Typparameter der Definition eines generischen Typs darstellen.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Gibt die dem aktuellen konstruierten Typ zugrunde liegende Definition eines generischen Typs zurück.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Gibt ein Array von `Type`\-Objekten zurück, die die Einschränkungen für den aktuellen generischen Typparameter darstellen.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Gibt true zurück, wenn der Typ oder einer seiner einschließenden Typen oder Methoden Typparameter enthält, für die bestimmte Typen nicht bereitgestellt wurden.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Ruft eine Kombination von `GenericParameterAttributes`\-Flags ab, die die besonderen Einschränkungen des aktuellen generischen Typparameters beschreiben.|  
|<xref:System.Type.GenericParameterPosition%2A>|Ruft für ein `Type`\-Objekt, das einen Typparameter darstellt, die Position des Typparameters in der Typparameterliste der Definition eines generischen Typs bzw. der Definition einer generischen Methode ab, mit der der Typparameter deklariert wurde.|  
|<xref:System.Type.IsGenericParameter%2A>|Ruft einen Wert ab, der angibt, ob der aktuelle `Type` einen Typparameter der Definition eines generischen Typs oder einer generischen Methode darstellt.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Ruft einen Wert ab, der angibt, ob der aktuelle <xref:System.Type> die Definition eines generischen Typs darstellt, auf dessen Grundlage andere generische Typen konstruiert werden können.  Gibt true zurück, wenn der Typ die Definition eines generischen Typs darstellt.|  
|<xref:System.Type.DeclaringMethod%2A>|Gibt die generische Methode zurück, mit der der aktuelle generische Typparameter definiert wurde, oder NULL, wenn der Typparameter nicht mit einer generischen Methode definiert wurde.|  
|<xref:System.Type.MakeGenericType%2A>|Ersetzt die Typparameter der Definition des aktuellen generischen Typs durch die Elemente eines Arrays von Typen und gibt ein <xref:System.Type>\-Objekt zurück, das den resultierenden konstruierten Typ darstellt.|  
  
 Zusätzlich werden der <xref:System.Reflection.MethodInfo>\-Klasse neue Member hinzugefügt, um Laufzeitinformationen für generische Methoden zu ermöglichen.  Eine Liste mit den invarianten Bedingungen für Begriffe, die für die Reflektion mit generischen Methoden verwendet werden, finden Sie in den Hinweisen zur <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>\-Eigenschaft.  
  
|System.Reflection.MemberInfo\-Membername|Beschreibung|  
|----------------------------------------------|------------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|Gibt true zurück, wenn eine Methode generisch ist.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Gibt ein Array von Type\-Objekten zurück, die die Typargumente einer konstruierten generischen Methode oder die Typparameter der Definition einer generischen Methode darstellen.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Gibt die der aktuellen konstruierten Methode zugrunde liegende Definition einer generischen Methode zurück.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Gibt true zurück, wenn die Methode oder einer ihrer einschließenden Typen Typparameter enthält, für die bestimmte Typen nicht bereitgestellt wurden.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Gibt true zurück, wenn das aktuelle <xref:System.Reflection.MethodInfo> die Definition einer generischen Methode darstellt.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Ersetzt die Typparameter der aktuellen generischen Methodendefinition durch die Elemente eines Arrays von Typen und gibt ein <xref:System.Reflection.MethodInfo>\-Objekt zurück, das die sich ergebende konstruierte Methode darstellt.|  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Reflektion und generische Typen](../Topic/Reflection%20and%20Generic%20Types.md)   
 [Generika](../Topic/Generics%20in%20the%20.NET%20Framework.md)