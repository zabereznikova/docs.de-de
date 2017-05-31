---
title: -appconfig (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /appconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: ced4927526d86d29c502a898c60c528df497bb56
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="appconfig-c-compiler-options"></a>/appconfig (C#-Compileroptionen)
Mit der Compileroption **/appconfig** kann eine C#-Anwendung den Speicherort der Anwendungskonfigurationsdatei („app.config“) der Assembly für die Common Language Runtime (CLR) zur Assemblybindungszeit festlegen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/appconfig:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Die Anwendungskonfigurationsdatei mit den Assemblybindungseinstellungen  
  
## <a name="remarks"></a>Hinweise  
 Der Gebrauch von **/appconfig** ist ein erweitertes Szenario, in dem eine Assembly gleichzeitig auf die Version von .NET Framework und von .NET Framework for Silverlight einer bestimmten Verweisassembly verweisen muss. Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer muss möglicherweise für die Benutzeroberfläche des Designers sowohl auf den WPF-Desktop als auch auf die Teilmenge von WPF, die in Silverlight enthalten ist, verweisen. Dieselbe Designerassembly muss auf beide Assembly zugreifen. Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.  
  
 Mit der Compileroption **/appconfig** können Sie den Speicherort einer app.config-Datei festlegen, die das Standardverhalten mit dem `<supportPortability>`-Tag deaktiviert, wie in folgendem Beispiel gezeigt.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 Der Compiler übergibt den Speicherort der Datei an die Assemblybindungslogik der CLR.  
  
> [!NOTE]
>  Wenn Sie das Microsoft-Buildmodul (MSBuild) verwenden, um Ihre Anwendung zu erstellen, können Sie die Compileroption **/appconfig** festlegen, indem Sie ein Eigenschaftentag in die CSPROJ-Datei einfügen. Fügen Sie den Eigenschaftentag `<UseAppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf `true` fest, um die app.config-Datei zu verwenden, die bereits im Projekt angegeben ist. Fügen Sie den Eigenschaftentag `<AppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf den Speicherort der Datei fest, um eine andere app.config-Datei anzugeben.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird eine app.config-Datei gezeigt, die es einer Anwendung ermöglicht, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder .NET Framework-Assembly zu verfügen, die in beiden Implementierungen vorhanden ist. Die Compileroption **/appconfig** gibt den Speicherort der app.config-Datei an.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die .NET Framework-Assemblyvereinheitlichung](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)   
 [\<supportPortability> Element](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)   
 [C#-Compileroptionen alphabetisch sortiert](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)
