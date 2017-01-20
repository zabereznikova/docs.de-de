---
title: "/linkresource (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkresource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/linkresource compiler option [C#]"
  - "linkres compiler option [C#]"
  - "/linkres compiler option [C#]"
  - "-linkres compiler option [C#]"
  - "-linkresource compiler option [C#]"
  - "linkresource compiler option [C#]"
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /linkresource (C# Compiler Options)
Erstellt einen Link zu einer .NET Framework\-Ressource in der Ausgabedatei.  Der Ausgabedatei wird die Ressourcendatei nicht hinzugefügt.  Dies unterscheidet von der [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)\-Option, die eine Ressourcendatei in die Ausgabedatei einbettet.  
  
## Syntax  
  
```  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Argumente  
 `filename`  
 die .NET Framework\-Ressourcendatei, zu der Sie von der Assembly aus eine Verknüpfung erstellen möchten.  
  
 `identifier` \(optional\)  
 Der logische Name der Ressource. Dieser wird zum Laden der Ressource verwendet.  Der Standardwert ist der Dateiname.  
  
 `accessibility-modifier` \(optional\)  
 Der Zugriff auf die Ressource: public oder private.  Der Standard lautet public.  
  
## Hinweise  
 Verknüpfte Ressourcen sind in der Assembly automatisch öffentlich, wenn sie mit dem C\#\-Compiler erstellt wurden.  Um die Ressource auf private umzustellen, geben Sie `private` als Zugriffsmodifizierer an.  Andere Modifizierer als `public` oder `private` sind nicht zugelassen.  
  
 Die Option **\/linkresource** erfordert eine andere [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)\-Option als **\/target:module**.  
  
 Wenn `filename` einer .NET Framework\-Ressourcendatei entspricht, die beispielsweise durch [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann mit Membern im <xref:System.Resources>\-Namespace darauf zugegriffen werden.  Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Für alle anderen Ressourcen verwenden Sie die `GetManifestResource`\*\-Methoden in der <xref:System.Reflection.Assembly>\-Klasse, um die Ressource zur Laufzeit aufzurufen.  
  
 Die unter `filename` angegebene Datei kann in beliebigem Format vorliegen.  Sie können beispielsweise eine systemeigene DLL zum Bestandteil der Assembly machen, damit sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  Im zweiten der folgenden Beispiele wird gezeigt, wie Sie dafür vorgehen müssen.  Dies ist auch im Assemblylinker möglich.  Dies wird im dritten der folgenden Beispiele gezeigt.  Weitere Informationen finden Sie unter [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) und [Arbeiten mit Assemblys und dem globalen Assemblychache](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md).  
  
 **\/linkres** ist die Kurzform von **\/linkresource**.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert und mit der Ressourcendatei `rf.resource` verknüpft:  
  
```  
csc /linkresource:rf.resource in.cs  
```  
  
## Beispiel  
 Kompilieren Sie `A.cs` in eine DLL, verknüpfen Sie sie mit einer systemeigenen DLL N.dll, und legen Sie die Ausgabe im globalen Assemblycache \(GAC\) ab.  In diesem Beispiel befinden sich sowohl A.dll als auch N.dll im globalen Assemblycache.  
  
```  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## Beispiel  
 Bei diesem Beispiel ist das Ergebnis mit dem vorherigen identisch, allerdings werden nun die Assemblylinkeroptionen verwendet.  
  
```  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)