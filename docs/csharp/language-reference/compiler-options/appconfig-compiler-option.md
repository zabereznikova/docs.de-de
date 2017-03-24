---
title: "/appconfig (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/appconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/appconfig compiler option [C#]"
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# /appconfig (C# Compiler Options)
Die **\/appconfig**\-Compileroption wird eine C\#\-Anwendung aktiviert, damit für den Speicherort der Anwendungskonfiguration einer Assembly der Datei \(app.config\) der Common Language Runtime \(CLR\) an der Assemblybindungszeit anzugeben.  
  
## Syntax  
  
```  
/appconfig:file  
```  
  
## Argumente  
 `file`  
 Erforderlich.  Die Konfigurationsdatei der Anwendung mit den Assemblybindungseinstellungen  
  
## Hinweise  
 Eine Verwendung von **\/appconfig** ist erweiterte Szenarien, in denen eine Assembly die .NET Framework\-Version und .NET Framework for Silverlight\-Version einer bestimmten Verweisassembly gleichzeitig verweisen muss.  Ein in Windows Presentation Foundation \(WPF\) geschriebener XAML\-Designer müsste möglicherweise sowohl auf den WPF\-Desktop, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in Silverlight enthalten ist, verweisen.  Dieselbe Designerassembly muss auf beide Assemblys zugreifen.  Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.  
  
 Die **\/appconfig**\-Compileroption ermöglicht es Ihnen, den Speicherort einer app.config\-Datei anzugeben, die das Standardverhalten mit einem `<supportPortability>`\-Tag deaktiviert, wie im folgenden Beispiel gezeigt.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 Der Compiler übergibt den Speicherort der Datei an die Assemblybindungslogik der CLR.  
  
> [!NOTE]
>  Wenn Sie Microsoft Build Engine \(MSBuild\) verwenden, um die Anwendung zu erstellen, können Sie die **\/appconfig**\-Compileroption festlegen, indem Sie ein Eigenschaftentag zur CSPROJ\-Datei hinzufügen.  Um die Datei app.config zu verwenden, die bereits im Projekt festgelegt ist, fügen Sie der CSPROJ\-Datei das Eigenschaftstag `<UseAppConfigForCompiler>` hinzu, und legen Sie seinen Wert auf `true` fest.  Um eine andere app.config\-Datei Eigenschaft anzugeben, fügen Sie das Eigenschaftstag `<AppConfigForCompiler>` hinzu, und legen Sie seinen Wert auf den Speicherort der Datei fest.  
  
## Beispiel  
 Im folgenden Beispiel wird eine app.config\-Datei gezeigt, die es einer Anwendung ermöglicht, über Verweise sowohl auf die .NET Framework\-Implementierung als auch die .NET Framework for Silverlight\-Implementierung jeder beliebigen .NET Framework\-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen.  Die **\/appconfig**\-Compileroption gibt den Speicherort dieser app.config.Datei an.  
  
```  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/de-de/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)   
 [\<supportPortability\>\-Element](../Topic/%3CsupportPortability%3E%20Element.md)   
 [C\# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)