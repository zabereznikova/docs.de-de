---
title: "-Subsystemversion (C#-Compileroptionen) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# /subsystemversion (C#-Compileroptionen)
Gibt die Mindestversion des Subsystems, auf dem die generierte ausführbare Datei ausführen kann, und bestimmen die Versionen von Windows auf dem die ausführbare Datei ausgeführt werden kann. In den meisten Fällen wird diese Option sichergestellt, die ausführbare Datei bestimmte Sicherheitsfunktionen nutzen, die nicht mit älteren Versionen von Windows verfügbar sind.  
  
> [!NOTE]
>  Verwenden Sie zum Angeben der Subsystem selbst die [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) (Compileroption).  
  
## <a name="syntax"></a>Syntax  
  
```  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parameter  
 `major.minor`  
 Die mindestens erforderliche Version des Subsystems, ausgedrückt in eine punktierte Schreibweise für Haupt-und Nebenversionen. Beispielsweise können Sie angeben, dass eine Anwendung unter einem Betriebssystem werden, die älter als Windows 7 ausgeführt kann wenn 6.01, den Wert dieser Option fest, wie in der Tabelle weiter unten in diesem Thema beschrieben. Geben Sie die Werte für `major` und `minor` als ganze Zahlen.  
  
 Führende Nullen in der `minor` Version nicht die Version geändert, aber nachfolgende Nullen werden. Z. B. 6.1 und 6.01 beziehen sich auf die gleiche Version, aber 6.10 bezieht sich auf eine andere Version. Es wird empfohlen, die Nebenversion auszudrücken, als zwei Ziffern, um Verwechslungen zu vermeiden.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.  
  
|Windows-Version|Subsystem-version|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Standardwerte  
 Der Standardwert der **/subsystemversion** (Compileroption) hängt von der Bedingung in der folgenden Liste:  
  
-   Der Standardwert ist 6.02, wenn jede Compileroption in der folgenden Liste festgelegt wird:  
  
    -   [/ target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/ target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/Platform:ARM](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   Der Standardwert ist 6.00, wenn Sie MSBuild verwenden, die Sie als Ziel [!INCLUDE[net_v45](~/includes/net-v45-md.md)], und Sie können alle Compileroptionen, die zuvor in dieser Liste angegeben wurden noch nicht festlegen.  
  
-   Der Standardwert ist 4.00, wenn keine der vorherigen Bedingungen true ist.  
  
## <a name="setting-this-option"></a>Festlegen dieser Option  
 Festlegen der **/subsystemversion** -Compileroption in Visual Studio müssen Sie öffnen Sie die CSPROJ-Datei und geben Sie einen Wert für die `SubsystemVersion` Eigenschaft in der MSBuild-XML. Diese Option kann nicht in der Visual Studio-IDE festgelegt werden. Weitere Informationen finden Sie unter "Standardwerte" weiter oben in diesem Thema oder [gemeinsame MSBuild-Projekteigenschaften](/visual-studio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)