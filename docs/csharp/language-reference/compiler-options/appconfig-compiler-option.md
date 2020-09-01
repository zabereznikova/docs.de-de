---
description: -appconfig (C#-Compileroptionen)
title: -appconfig (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 287d41105199057add1dad78d480b083adb745b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126111"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="27ca4-103">-appconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="27ca4-103">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="27ca4-104">Mit der Compileroption **-appconfig** kann eine C#-Anwendung den Speicherort der Anwendungskonfigurationsdatei („app.config“) der Assembly für die Common Language Runtime (CLR) zur Assemblybindungszeit festlegen.</span><span class="sxs-lookup"><span data-stu-id="27ca4-104">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ca4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="27ca4-105">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="27ca4-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="27ca4-106">Arguments</span></span>  
 `file`  
 <span data-ttu-id="27ca4-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27ca4-107">Required.</span></span> <span data-ttu-id="27ca4-108">Die Anwendungskonfigurationsdatei mit den Assemblybindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="27ca4-108">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27ca4-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="27ca4-109">Remarks</span></span>  
 <span data-ttu-id="27ca4-110">Der Gebrauch von **-appconfig** stellt ein erweitertes Szenario dar, in dem eine Assembly gleichzeitig auf die Version von .NET Framework und von .NET Framework for Silverlight einer bestimmten Verweisassembly verweisen muss.</span><span class="sxs-lookup"><span data-stu-id="27ca4-110">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="27ca4-111">Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer muss möglicherweise für die Benutzeroberfläche des Designers sowohl auf den WPF-Desktop als auch auf die Teilmenge von WPF, die in Silverlight enthalten ist, verweisen.</span><span class="sxs-lookup"><span data-stu-id="27ca4-111">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="27ca4-112">Dieselbe Designerassembly muss auf beide Assembly zugreifen.</span><span class="sxs-lookup"><span data-stu-id="27ca4-112">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="27ca4-113">Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.</span><span class="sxs-lookup"><span data-stu-id="27ca4-113">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="27ca4-114">Mit der Compileroption **-appconfig** können Sie den Speicherort einer app.config-Datei festlegen, die das Standardverhalten wie im folgenden Beispiel dargestellt mit dem `<supportPortability>`-Tag deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="27ca4-114">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="27ca4-115">Der Compiler übergibt den Speicherort der Datei an die Assemblybindungslogik der CLR.</span><span class="sxs-lookup"><span data-stu-id="27ca4-115">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27ca4-116">Wenn Sie die Microsoft-Build-Engine (MSBuild) verwenden, um Ihre Anwendung zu erstellen, können Sie die Compileroption **-appconfig** festlegen, indem Sie ein Eigenschaftentag in die CSPROJ-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="27ca4-116">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="27ca4-117">Fügen Sie den Eigenschaftentag `<UseAppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf `true` fest, um die app.config-Datei zu verwenden, die bereits im Projekt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="27ca4-117">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="27ca4-118">Fügen Sie den Eigenschaftentag `<AppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf den Speicherort der Datei fest, um eine andere app.config-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="27ca4-118">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ca4-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27ca4-119">Example</span></span>  
 <span data-ttu-id="27ca4-120">In folgendem Beispiel wird eine app.config-Datei gezeigt, die es einer Anwendung ermöglicht, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder .NET Framework-Assembly zu verfügen, die in beiden Implementierungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="27ca4-120">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="27ca4-121">Die Compileroption **-appconfig** gibt den Speicherort der app.config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="27ca4-121">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27ca4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27ca4-122">See also</span></span>

- [<span data-ttu-id="27ca4-123">\<supportPortability>-Element</span><span class="sxs-lookup"><span data-stu-id="27ca4-123">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [<span data-ttu-id="27ca4-124">C#-Compileroptionen alphabetisch sortiert</span><span class="sxs-lookup"><span data-stu-id="27ca4-124">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
