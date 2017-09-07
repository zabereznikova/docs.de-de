---
title: -subsystemversion (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c7992086eb33577d795496025820ed8f7bb51c24
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="subsystemversion-c-compiler-options"></a>/subsystemversion (C#-Compileroptionen)
Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann. In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.  
  
> [!NOTE]
>  Verwenden Sie zum Angeben des Subsystems selbst die Compileroption [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).  
  
## <a name="syntax"></a>Syntax  
  
```console  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parameter  
 `major.minor`  
 Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt. Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird. Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.  
  
 Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen. 6.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version. Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.  
  
|Windows-Version|Subsystemversion|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Standardwerte  
 Der Standardwert der Compileroption **/subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:  
  
-   Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:  
  
    -   [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [/platform:arm](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   Beim Verwenden von MSBuild ist der Standardwert 6,00, indem Sie [!INCLUDE[net_v45](~/includes/net-v45-md.md)] als Ziel setzen, und Sie haben keine der Compileroptionen festgelegt, die zuvor in der Liste angegeben wurden.  
  
-   Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.  
  
## <a name="setting-this-option"></a>Festlegen dieser Option  
 Sie müssen die CSPROJ-Datei öffnen und einen Wert für die Eigenschaft `SubsystemVersion` im MSBuild-XML angeben, um die Compileroption **/subsystemversion** in Visual Studio festzulegen. Diese Option kann nicht in der Visual Studio-IDE festgelegt werden. Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)

