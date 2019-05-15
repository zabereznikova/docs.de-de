---
title: 'Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d785ae9b3bce0b5c77414057ef063d6e9d3e14a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593587"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a>Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne
Es gibt mehrere Möglichkeiten, eine Assembly in eine Anwendungsdomäne zu laden. Es wird empfohlen, die `static` <xref:System.Reflection.Assembly.Load%2A>-Methode (`Shared` in Visual Basic) der Klasse <xref:System.Reflection.Assembly?displayProperty=nameWithType> zu verwenden. Es gibt noch weitere Möglichkeiten, Assemblys zu laden:  
  
- Die <xref:System.Reflection.Assembly.LoadFrom%2A>-Methode der Klasse <xref:System.Reflection.Assembly> lädt eine Assembly, sofern deren Speicherort angegeben wird. Beim Laden von Assemblys mit dieser Methode wird ein anderer Load-Kontext verwendet.  
  
- Die Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> und <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> laden eine Assembly in den ReflectionOnly-Kontext. In diesen Kontext geladene Assemblys können untersucht, aber nicht ausgeführt werden. So können Assemblys untersucht werden, die andere Zielplattformen aufweisen. Weitere Informationen finden Sie unter [How to: Laden von Assemblys in den reflexionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  Der ReflectionOnly-Kontext ist neu in .NET Framework Version 2.0.  
  
- Methoden der <xref:System.AppDomain>-Klasse, wie etwa <xref:System.AppDomain.CreateInstance%2A> und <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>, können Assemblys in eine Anwendungsdomäne laden.  
  
- Die <xref:System.Type.GetType%2A>-Methode der <xref:System.Type>-Klasse kann Assemblys laden.  
  
- Die <xref:System.AppDomain.Load%2A>-Methode der <xref:System.AppDomain?displayProperty=nameWithType>-Klasse kann Assemblys laden, wird aber hauptsächlich für COM-Interoperabilität verwendet. Sie sollte nicht zum Laden von Assemblys in eine andere als diejenige Anwendungsdomäne verwendet werden, aus der sie geladen wurde.  
  
> [!NOTE]
>  Ab .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladene Runtime besitzt. Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.  
  
 Sie können angeben, wie der kompilierte Just-In-Time-Code (JIT) aus geladenen Assemblys von mehreren Anwendungsdomänen gemeinsam verwendet wird. Weitere Informationen finden Sie unter [Application Domains and Assemblies (Anwendungsdomänen und Assemblys)](application-domains.md#application-domains-and-assemblies).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code lädt eine Assembly mit dem Namen „example.exe“ oder „example.dll“ in die aktuelle Anwendungsdomäne, ruft einen Typ mit dem Namen `Example` aus der Assembly ab, ruft für diesen Typ eine Methode mit dem Namen `MethodA` ohne Parameter ab, und führt die Methode aus. Eine vollständige Erläuterung des Abrufens von Informationen aus einer geladenen Assembly finden Sie unter [Dynamically Loading and Using Types (Dynamisches Laden und Verwenden von Typen)](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](application-domains.md#programming-with-application-domains)
- [Reflexion](../../../docs/framework/reflection-and-codedom/reflection.md)
- [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)
- [Vorgehensweise: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Gewusst wie: Laden von Assemblys in den auf Reflektion beschränkten Kontext)
- [Anwendungsdomänen und Assemblys](application-domains.md#application-domains-and-assemblies)
