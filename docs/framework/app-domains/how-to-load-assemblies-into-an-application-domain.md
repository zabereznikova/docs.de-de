---
title: "Gewusst wie: Laden von Assemblys in eine Anwendungsdom&#228;ne | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsdomänen, Laden von Assemblys"
  - "Laden von Assemblys"
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Laden von Assemblys in eine Anwendungsdom&#228;ne
Es gibt mehrere Möglichkeiten, eine Assembly in eine Anwendungsdomäne zu laden.  Es wird empfohlen, hierzu die `static` \(`Shared` in Visual Basic\) <xref:System.Reflection.Assembly.Load%2A>\-Methode der [System.Reflection.Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)\-Klasse zu verwenden.  Darüber hinaus können Assemblys u. a. auf folgende Arten geladen werden:  
  
-   Die <xref:System.Reflection.Assembly.LoadFrom%2A>\-Methode der [Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)\-Klasse lädt eine Assembly anhand ihres Dateispeicherorts.  Wenn Assemblys mit dieser Methode geladen werden, wird ein anderer Ladekontext verwendet.  
  
-   Die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>\-Methode und die <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>\-Methode laden eine Assembly in den reflektionsbezogenen Kontext.  Assemblys, die in diesen Kontext geladen werden, können überprüft, aber nicht ausgeführt werden, wodurch eine Überprüfung von Assemblys ermöglicht wird, die für andere Plattformen vorgesehen sind.  Siehe [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  Der reflektionsbezogene Kontext ist neu in .NET Framework, Version 2.0.  
  
-   Methoden wie <xref:System.AppDomain.CreateInstance%2A> und <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> der <xref:System.AppDomain>\-Klasse können Assemblys in eine Anwendungsdomäne laden.  
  
-   Die <xref:System.Type.GetType%2A>\-Methode der <xref:System.Type>\-Klasse kann Assemblys laden.  
  
-   Die <xref:System.AppDomain.Load%2A>\-Methode der <xref:System.AppDomain?displayProperty=fullName>\-Klasse kann Assemblys laden, wird allerdings für die COM\-Interoperabilität verwendet.  Mit dieser Methode sollten Assemblys nur in die Anwendungsdomäne geladen werden, von der sie aufgerufen wird.  
  
> [!NOTE]
>  Ab .NET Framework, Version 2.0, lädt die Laufzeit keine Assemblys mehr, die mit einer Version von .NET Framework kompiliert wurden, deren Versionsnummer höher ist als die der aktuell geladenen Laufzeit.  Dies gilt für die Kombination aus den Haupt\- und Nebenkomponenten der Versionsnummer.  
  
 Sie können angeben, auf welche Weise der JIT\-kompilierte Code \(Just\-In\-Time\) aus geladenen Assemblys von Anwendungsdomänen gemeinsam genutzt wird.  Weitere Informationen finden Sie unter [Application Domains and Assemblies](http://msdn.microsoft.com/de-de/433b04ae-4ba8-4849-9dbd-79194f240346).  
  
## Beispiel  
 Mit dem folgenden Code wird eine Assembly namens "example.exe" oder "example.dll" in die aktuelle Anwendungsdomäne geladen, ein Typ namens `Example` aus der Assembly abgerufen, eine parameterlose Methode namens `MethodA` für diesen Typ abgerufen und die Methode ausgeführt.  Eine ausführliche Übersicht über das Abrufen von Informationen aus einer geladenen Assembly finden Sie unter [Dynamisches Laden und Verwenden von Typen](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Hosting Overview](http://msdn.microsoft.com/de-de/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/de-de/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)   
 [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Application Domains and Assemblies](http://msdn.microsoft.com/de-de/433b04ae-4ba8-4849-9dbd-79194f240346)