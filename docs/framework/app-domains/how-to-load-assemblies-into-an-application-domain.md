---
title: "Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 934373d61407c8cc19b7d6424898a582880f9c21
ms.openlocfilehash: c319da0f8e6f3cdfb83e659a778136d668699834
ms.contentlocale: de-de
ms.lasthandoff: 08/10/2017

---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne
Es gibt mehrere Möglichkeiten, eine Assembly in eine Anwendungsdomäne zu laden. Es wird empfohlen, die `static` <xref:System.Reflection.Assembly.Load%2A>-Methode (`Shared` in Visual Basic) der Klasse <xref:System.Reflection.Assembly?displayProperty=fullName> zu verwenden. Sie könne Assemblys u.a. auch so laden:  
  
-   Die <xref:System.Reflection.Assembly.LoadFrom%2A>-Methode der Klasse <xref:System.Reflection.Assembly> lädt eine Assembly mit deren Dateiort. Beim Laden von Assemblys mit dieser Methode wird ein anderer Load-Kontext verwendet.  
  
-   Die Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> und <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> laden eine Assembly in den ReflectionOnly-Kontext, wenn ihr Pfad angegeben wurde. In diesen Kontext geladenen Assemblys können untersucht, aber nicht ausgeführt werden. So können Assemblys untersucht werden, die andere Zielplattformen aufweisen. Weitere Informationen finden Sie unter [How to: Load Assemblies into the Reflection-Only Context (Vorgehensweise: Laden von Assemblys in den ReflectionOnly-Kontext)](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  Der ReflectionOnly-Kontext ist neu in .NET Framework Version 2.0.  
  
-   Methoden, wie etwa <xref:System.AppDomain.CreateInstance%2A> und <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>, der <xref:System.AppDomain>-Klasse können Assemblys in eine Anwendungsdomäne laden.  
  
-   Die <xref:System.Type.GetType%2A>-Methode der <xref:System.Type>-Klasse kann Assemblys laden.  
  
-   Die <xref:System.AppDomain.Load%2A>-Methode der <xref:System.AppDomain?displayProperty=fullName>-Klasse kann Assemblys laden, wird aber hauptsächlich für COM-Interoperabilität verwendet. Sie sollte nicht zum Laden von Assemblys in eine Anwendungsdomäne verwendet werde, bei der es sich nicht um die Anwendungsdomäne handelt, aus der sie geladen wurde.  
  
> [!NOTE]
>  Ab der .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladenen Runtime besitzt. Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.  
  
 Sie können angeben, wie der kompilierte Just-In-Time-Code (JIT) aus geladenen Assemblys zwischen Anwendungsdomänen freigegeben wird. Weitere Informationen zu Anwendungsdomänen finden Sie unter [Application Domains and Assemblies (Anwendungsdomänen und Assemblys)](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346).  
  
## <a name="example"></a>Beispiel  
 Der folgend Code lädt eine Assembly mit dem Namen „beispiel.exe“ oder „beispiel.dll“ in die aktuelle Anwendungsdomäne, ruft einen Typ mit dem Namen `Example` aus der Assembly ab, ruft für diesen Typ eine Methode mit dem Namen `MethodA` ohne Parameter ab, und führt die Methode aus. Eine vollständige Erläuterung des Abrufens von Informationen von einer geladenen Assembly finden Sie unter [Dynamically Loading and Using Types (Dynamisches Laden und Verwenden von Typen)](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)] [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)] [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Programmieren mit Anwendungsdomänen](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflection (Reflektion)](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Using Application Domains (Verwenden von Anwendungsdomänen)](../../../docs/framework/app-domains/use.md)   
 [Vorgehensweise: Laden von Assemblys in den ReflectionOnly-Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Anwendungsdomänen und Assemblys](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)

