---
title: Anpassen der verfügbaren Objekte in "My"
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: 5245c129281bc8c7c1c6fe9215a221889380a901
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410217"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Anpassen der verfügbaren Objekte in "My" (Visual Basic)

In diesem Thema wird beschrieben, wie Sie steuern können, welche `My`-Objekte aktiviert werden, indem Sie die Konstante für bedingte Kompilierung `_MYTYPE` Ihres Projekts festlegen. Die integrierte Visual Studio-Entwicklungsumgebung (Integrated Development Environment, IDE) sorgt dafür, dass die Konstante für bedingte Kompilierung `_MYTYPE` für ein Projekt zum jeweiligen Projekttyp passt.  
  
## <a name="predefined-_mytype-values"></a>Vordefinierte \_MYTYPE-Werte  

Sie müssen die Compileroption `/define` verwenden, um die Konstante für bedingte Kompilierung `_MYTYPE` festzulegen. Wenn Sie einen eigenen Wert für die Konstante `_MYTYPE` angeben, müssen Sie den Zeichenfolgenwert in Sequenzen mit umgekehrten Schrägstrichen und Anführungszeichen (\\") einschließen. Sie können z. B. Folgendes angeben:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 In der folgenden Tabelle sind die für die Konstante für bedingte Kompilierung `_MYTYPE` festgelegten Werte für verschiedene Projekttypen dargestellt.  
  
|Projekttyp:|\_MYTYPE-Wert|  
|------------------|--------------------|  
|Klassenbibliothek|"Windows"|  
|Konsolenanwendung|"Console"|  
|Web|"Web"|  
|Websteuerelementbibliothek|"WebControl"|  
|Windows-Anwendung|"WindowsForms"|  
|Windows-Anwendung, wenn sie mit einer benutzerdefinierten `Sub Main`-Methode beginnt|"WindowsFormsWithCustomSubMain"|  
|Windows-Steuerelementbibliothek|"Windows"|  
|Windows-Dienst|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
> Die Groß-/Kleinschreibung wird bei allen Zeichenfolgenvergleichen für bedingte Kompilierung beachtet, unabhängig davon, was für die Anweisung `Option Compare` festgelegt ist.  
  
## <a name="dependent-_my-compilation-constants"></a>Abhängige \_MY-Kompilierungskonstanten  

Die Konstante für bedingte Kompilierung `_MYTYPE` steuert wiederum die Werte mehrere anderer `_MY`-Kompilierungskonstanten:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Nicht definiert|"Windows"|true|  
|"Custom"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Empty"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Web"|Nicht definiert|"Web"|false|"Web"|false|  
|"WebControl"|Nicht definiert|"Web"|false|"Web"|true|  
|"Windows" oder ""|"Windows"|"Windows"|Nicht definiert|"Windows"|true|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|true|"Windows"|true|  
  
 Nicht definierte Konstanten für bedingte Kompilierung werden standardmäßig in `FALSE` aufgelöst. Sie können beim Kompilieren Ihres Projekts Werte für die nicht definierten Konstanten festlegen, um das Standardverhalten außer Kraft zu setzen.  
  
> [!NOTE]
> Wenn für `_MYTYPE` "Custom" festgelegt ist, enthält das Projekt zwar den `My`-Namespace, aber keine Objekte. Das Festlegen von "Empty" für `_MYTYPE` verhindert allerdings, dass der Compiler den `My`-Namespace und dessen Objekte hinzufügt.  
  
 In der folgenden Tabelle werden die Auswirkungen der vordefinierten Werte auf die `_MY`-Kompilierungskonstanten beschrieben.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Diese Konstante aktiviert `My.Application`, wenn "Console", Windows" oder "WindowsForms" festgelegt ist:<br /><br /> – Die "Console"-Version ist aus <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> abgeleitet und verfügt über weniger Member als die "Windows"-Version.<br />– Die "Windows"-Version ist aus <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> abgeleitet und verfügt über weniger Member als die "WindowsForms"-Version.<br />– Die "WindowsForms"-Version von `My.Application` ist aus <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> abgeleitet. Wenn die Konstante `TARGET` als "winexe" definiert ist, beinhaltet die Klasse eine `Sub Main`-Methode.|  
|`_MYCOMPUTERTYPE`|Diese Konstante aktiviert `My.Computer`, wenn "Web" oder "Windows" festgelegt ist:<br /><br /> – Die "Web"-Version ist aus <xref:Microsoft.VisualBasic.Devices.ServerComputer> abgeleitet und verfügt über weniger Member als die "Windows"-Version.<br />– Die "Windows"-Version von `My.Computer` ist aus <xref:Microsoft.VisualBasic.Devices.Computer> abgeleitet.|  
|`_MYFORMS`|Diese Konstante aktiviert `My.Forms`, wenn `TRUE` festgelegt ist.|  
|`_MYUSERTYPE`|Diese Konstante aktiviert `My.User`, wenn "Web" oder "Windows" festgelegt ist:<br /><br /> – Die "Web"-Version von `My.User` ist mit der Benutzeridentität der aktuellen HTTP-Anforderung verknüpft.<br />– Die "Windows"-Version von `My.User` ist mit dem aktuellen Prinzipal des Threads verknüpft.|  
|`_MYWEBSERVICES`|Diese Konstante aktiviert `My.WebServices`, wenn `TRUE` festgelegt ist.|  
|`_MYTYPE`|Diese Konstante aktiviert `My.Log`, `My.Request` und `My.Response`, wenn "Web" festgelegt ist.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Merkmale von "My" auf Grundlage des Projekttyps](../development-with-my/how-my-depends-on-project-type.md)
- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../language-reference/objects/my-webservices-object.md)
