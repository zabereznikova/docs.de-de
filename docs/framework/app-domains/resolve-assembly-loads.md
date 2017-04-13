---
title: "Aufl&#246;sen beim Laden von Assemblys | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Auflösen beim Laden"
  - "Anwendungsdomänen, Laden von Assemblys"
  - "Auflösen beim Laden von Assemblys"
  - "Assemblys [.NET Framework], laden"
  - "Anwendungsdomänen, Auflösen beim Laden von Assemblys"
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Aufl&#246;sen beim Laden von Assemblys
.NET Framework stellt das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis für Anwendungen bereit, die umfassendere Steuerungsmöglichkeiten beim Laden von Assemblys erfordern.  Durch Behandlung dieses Ereignisses kann Ihre Anwendung eine Assembly von Speicherorten außerhalb der normalen Prüfpfade in den Load\-Kontext laden, die zu ladenden Assemblyversionen auswählen, eine dynamische Assembly ausgeben und zurückgeben usw.  Dieses Thema enthält Anleitungen für die Behandlung des <xref:System.AppDomain.AssemblyResolve>\-Ereignisses.  
  
> [!NOTE]
>  Um das Laden von Assemblys im reflektionsbezogenen Kontext aufzulösen, verwenden Sie stattdessen das <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=fullName>\-Ereignis.  
  
## So funktioniert das AssemblyResolve\-Ereignis  
 Wenn Sie einen Handler für das <xref:System.AppDomain.AssemblyResolve>\-Ereignis registrieren, wird dieser Handler immer dann aufgerufen, wenn die Laufzeit eine Assembly nicht nach dem Namen binden kann.  Das Aufrufen der folgenden Methoden im Benutzercode kann beispielsweise dazu führen, dass das <xref:System.AppDomain.AssemblyResolve>\-Ereignis ausgelöst wird:  
  
-   Eine <xref:System.AppDomain.Load%2A?displayProperty=fullName>\-Methodenüberladung oder eine <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methodenüberladung, deren erstes Argument eine Zeichenfolge ist, die den Anzeigenamen der zu ladenden Assembly darstellt \(d. h. die von der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene Zeichenfolge\).  
  
-   Eine <xref:System.AppDomain.Load%2A?displayProperty=fullName>\-Methodenüberladung oder eine <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methodenüberladung, deren erstes Argument ein <xref:System.Reflection.AssemblyName>\-Objekt ist, das die zu ladende Assembly bezeichnet.  
  
-   Eine <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>\-Methodenüberladung.  
  
-   Eine <xref:System.AppDomain.CreateInstance%2A?displayProperty=fullName>\-Methodenüberladung oder eine <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName>\-Methodenüberladung, die ein Objekt in einer anderen Anwendungsdomäne instanziiert.  
  
### So funktioniert der Ereignishandler  
 Der Handler für das <xref:System.AppDomain.AssemblyResolve>\-Ereignis empfängt den Anzeigenamen der zu ladenden Assembly in der <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName>\-Eigenschaft.  Wenn der Handler den Assemblynamen nicht erkennt, wird NULL zurückgegeben \(`Nothing` in Visual Basic, `nullptr` in Visual C\+\+\).  
  
 Wenn der Handler den Assemblynamen erkennt, kann er eine Assembly laden und zurückgeben, die die Anforderung erfüllt.  In der folgenden Liste werden einige Beispielszenarien beschrieben.  
  
-   Wenn der Handler den Speicherort einer Version der Assembly kennt, kann er die Assembly unter Verwendung der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>\-Methode oder der <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>\-Methode laden und bei erfolgreicher Durchführung die geladene Assembly zurückgeben.  
  
-   Wenn der Handler Zugriff auf eine Datenbank mit Assemblys hat, die als Bytearrays gespeichert sind, kann er ein Bytearray laden. Hierzu wird eine der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methodenüberladungen verwendet, die ein Bytearray annehmen.  
  
-   Der Handler kann eine dynamische Assembly generieren und zurückgeben.  
  
> [!NOTE]
>  Der Handler muss die Assembly in den LoadFrom\-Kontext, in den Ladekontext oder ohne Kontext laden.  Wenn der Handler die Assembly unter Verwendung der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=fullName>\-Methode oder der <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=fullName>\-Methode in den reflektionsbezogenen Kontext lädt, schlägt der Ladeversuch, der das <xref:System.AppDomain.AssemblyResolve>\-Ereignis ausgelöst hat, fehl.  
  
 Es liegt in der Verantwortung des Ereignishandlers, eine geeignete Assembly zurückzugeben.  Der Handler kann den Anzeigenamen der angeforderten Assembly analysieren, indem er den <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName>\-Eigenschaftswert an den <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>\-Konstruktor übergibt.  Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] kann der Handler die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName>\-Eigenschaft verwenden, um zu bestimmen, ob die aktuelle Anforderung eine Abhängigkeit einer anderen Assembly darstellt.  Diese Informationen können dabei helfen, eine Assembly zu identifizieren, die die Abhängigkeit erfüllt.  
  
 Der Ereignishandler kann eine andere Version als die angeforderte Version der Assembly zurückgeben.  
  
 In den meisten Fällen wird die vom Handler zurückgegebene Assembly im Ladekontext enthalten sein, unabhängig vom Kontext, in den der Handler lädt.  Wenn der Handler zum Beispiel die <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>\-Methode verwendet, um eine Assembly in den LoadFrom\-Kontext zu laden, ist die Assembly im Ladekontext enthalten, wenn sie vom Handler zurückgegeben wird.  Im folgenden Fall erscheint die Assembly jedoch ohne Kontext, wenn sie vom Handler zurückgegeben wird:  
  
-   Der Handler lädt eine Assembly ohne Kontext.  
  
-   Die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName>\-Eigenschaft ist nicht NULL.  
  
-   Die anfordernde Assembly \(d. h. die von der <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene Assembly\) wurde ohne Kontext geladen.  
  
 Weitere Informationen zu Kontexten finden Sie unter der <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=fullName> Methodenüberladung.  
  
 Mehrere Versionen einer Assembly können in dieselbe Anwendungsdomäne geladen werden.  Diese Vorgehensweise wird nicht empfohlen, da sie zu Problemen bei der Zuweisung führen kann.  Siehe [Best Practices für das Laden von Assemblys](../../../docs/framework/deployment/best-practices-for-assembly-loading.md).  
  
### Nicht empfohlene Verwendung des Ereignishandlers  
 Die Hauptregel für die Behandlung des <xref:System.AppDomain.AssemblyResolve>\-Ereignisses besteht darin, nicht zu versuchen, eine nicht erkannte Assembly zurückzugeben.  Wenn Sie den Handler erstellen, sollten Sie wissen, welche Assemblys möglicherweise das Ereignis auslösen.  Der Handler sollte für andere Assemblys NULL zurückgeben.  
  
> [!IMPORTANT]
>  Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] wird das <xref:System.AppDomain.AssemblyResolve>\-Ereignis für Satellitenassemblys ausgelöst.  Diese Änderung betrifft einen Ereignishandler, der für eine frühere Version von .NET Framework geschrieben wurde, wenn der Handler versucht, alle Anforderungen für das Laden von Assemblys aufzulösen.  Ereignishandler, die nicht erkannte Assemblys ignorieren, sind von dieser Änderung nicht betroffen: Sie geben NULL zurück, und normale Fallbackmechanismen werden befolgt.  
  
 Beim Laden einer Assembly darf der Ereignishandler keine der <xref:System.AppDomain.Load%2A?displayProperty=fullName>\-Methodenüberladungen oder der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methodenüberladungen verwenden, die das rekursive Auslösen des <xref:System.AppDomain.AssemblyResolve>\-Ereignisses verursachen können, da dies zu einem Stapelüberlauf führen kann. \(Weitere Informationen finden Sie in der Liste weiter oben in diesem Thema.\) Dies tritt auch dann ein, wenn Sie eine Ausnahmebehandlung für die Ladeanforderung bereitstellen, da keine Ausnahme ausgelöst wird, bis alle Ereignishandler zurückgegeben wurden.  Somit führt der folgende Code zu einem Stapelüberlauf, wenn `MyAssembly` nicht gefunden wird:  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)]
 [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)]
 [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## Siehe auch  
 [Best Practices für das Laden von Assemblys](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)