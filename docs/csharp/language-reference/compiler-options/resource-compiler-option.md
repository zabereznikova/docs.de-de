---
title: "/resource (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/resource"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-resource compiler option [C#]"
  - "/resource compiler option [C#]"
  - "-res compiler option [C#]"
  - "/res compiler option [C#]"
  - "res compiler option [C#]"
  - "resource compiler option [C#]"
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /resource (C# Compiler Options)
Bettet die angegebene Ressource in die Ausgabedatei ein.  
  
## Syntax  
  
```  
/resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## Argumente  
 `filename`  
 die .NET Framework\-Ressourcendatei, die in die Ausgabedatei eingebettet werden soll.  
  
 `identifier` \(optional\)  
 Der logische Name der Ressource. Dieser wird zum Laden der Ressource verwendet.  Standardmäßig ist dies der Dateiname.  
  
 `accessibility-modifier` \(optional\)  
 Der Zugriff auf die Ressource: public oder private.  Der Standard lautet public.  
  
## Hinweise  
 Verwenden Sie die Option [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), wenn Sie eine Ressource mit einer Assembly verknüpfen möchten und die Ressourcendatei nicht in der Ausgabedatei platziert werden soll.  
  
 Ressourcen sind in der Assembly automatisch öffentlich, wenn sie mit dem C\#\-Compiler erstellt wurden.  Um die Ressource auf private umzustellen, geben Sie `private` als Zugriffsmodifizierer an.  Andere Zugriffe als `public` oder `private` sind nicht zugelassen.  
  
 Wenn `filename` einer .NET Framework\-Ressourcendatei entspricht, die beispielsweise durch [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann mit Membern im <xref:System.Resources>\-Namespace darauf zugegriffen werden.  Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=fullName>.  Für alle anderen Ressourcen verwenden Sie die `GetManifestResource`\*\-Methoden in der <xref:System.Reflection.Assembly>\-Klasse, um die Ressource zur Laufzeit aufzurufen.  
  
 **\/res** ist die Kurzform von **\/resource**.  
  
 Die Reihenfolge der Ressourcen in der Ausgabedatei ist durch die an der Befehlszeile angegebene Reihenfolge festgelegt.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Fügen Sie dem Projekt eine Ressourcendatei hinzu.  
  
2.  Wählen Sie im **Projektmappen\-Explorer** die einzubettende Datei aus.  
  
3.  Wählen Sie für die Datei im **Eigenschaftenfenster** die Option **Buildaktion** aus.  
  
4.  Legen Sie **Buildaktion** auf **Eingebettete Ressource** fest.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert und die Ressourcendatei `rf.resource` angefügt:  
  
```  
csc /resource:rf.resource in.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)