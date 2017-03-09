---
title: "Customizing Which Objects are Available in My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Customizing Which Objects are Available in My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie in einem Projekt durch Festlegen der `_MYTYPE`\-Konstante für die bedingte Kompilierung definiert werden kann, welche `My`\-Objekte aktiviert werden.  Die integrierte Entwicklungsumgebung \(IDE\) von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] passt die `_MYTYPE`\-Konstante für die bedingte Kompilierung in einem Projekt an den Typ des Projekts an.  
  
## Vordefinierte \_MYTYPE\-Werte  
 Die `_MYTYPE`\-Konstante für die bedingte Kompilierung wird mit der Compileroption `/define` festgelegt.  Beim Angeben benutzerdefinierter Werte für die `_MYTYPE`\-Konstante müssen Sie den Zeichenfolgenwert am Anfang und Ende mit einem umgekehrten Schrägstrich und einem Anführungszeichen \(\\"\) umschließen.  Sie könnten z. B. folgende Angabe verwenden:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 In dieser Tabelle wird der Wert der `_MYTYPE`\-Konstante für die bedingte Kompilierung für verschiedene Projekttypen aufgeführt.  
  
|Projekttyp|\_MYTYPE\-Wert|  
|----------------|--------------------|  
|Klassenbibliothek|"Windows"|  
|Konsolenanwendung|"Console"|  
|Internet|"Web"|  
|Web\-Steuerelementbibliothek|"WebControl"|  
|Windows\-Anwendung|"WindowsForms"|  
|Windows\-Anwendung bei Start mit benutzerdefiniertem `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows\-Steuerelementbibliothek|"Windows"|  
|Windows\-Dienst|"Console"|  
|Leer|"Empty"|  
  
> [!NOTE]
>  Unabhängig von der Einstellung für die `Option Compare`\-Anweisung wird bei allen Zeichenfolgenvergleichen für die bedingte Kompilierung die Groß\- und Kleinschreibung berücksichtigt.  
  
## Abhängige \_MY\-Kompilierungskonstanten  
 Die `_MYTYPE`\-Konstante für die bedingte Kompilierung beeinflusst den Wert mehrerer anderer `_MY`\-Kompilierungskonstanten, wie im Folgenden dargestellt:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Nicht definiert|"Windows"|TRUE|  
|"Custom"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Empty"|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|"Web"|Nicht definiert|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|Nicht definiert|"Web"|FALSE|"Web"|TRUE|  
|"Windows" oder ""|"Windows"|"Windows"|Nicht definiert|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 Standardmäßig wird nicht definierten Konstanten für die bedingte Kompilierung der Wert `FALSE` zugeordnet.  Sie können beim Kompilieren des Projekts Werte für die nicht definierten Konstanten angeben, um das Standardverhalten zu überschreiben.  
  
> [!NOTE]
>  Wenn `_MYTYPE` auf "Custom" festgelegt wird, enthält das Projekt den `My`\-Namespace, aber keine Objekte.  Wenn `_MYTYPE` auf "Empty" festgelegt ist, fügt der Compiler den `My`\-Namespace und die zugehörigen Objekte nicht hinzu.  
  
 In dieser Tabelle wird die Bedeutung der vordefinierten Werte der `_MY`\-Kompilierungskonstanten beschrieben.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_MYAPPLICATIONTYPE`|Aktiviert `My.Application`, wenn die Konstante den Wert "Console", "Windows" oder "WindowsForms" aufweist.<br /><br /> -   Die Console\-Version ist von <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> abgeleitet  und verfügt über weniger Member als die Windows\-Version.<br />-   Die "Windows"\-Version ist von <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> abgeleitet und weist weniger Member als die "WindowsForms"\-Version auf.<br />-   Die "WindowsForms"\-Version von `My.Application` ist von <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> abgeleitet.  Wenn die `TARGET`\-Konstante auf den Wert "winexe" festgelegt wurde, verfügt die Klasse über eine `Sub Main`\-Methode.|  
|`_MYCOMPUTERTYPE`|Aktiviert `My.Computer`, wenn die Konstante den Wert "Web" oder "Windows" aufweist:<br /><br /> -   Die "Web"\-Version ist von <xref:Microsoft.VisualBasic.Devices.ServerComputer> abgeleitet und weist weniger Member als die "Windows"\-Version auf.<br />-   Die "Windows"\-Version von `My.Computer` ist von <xref:Microsoft.VisualBasic.Devices.Computer> abgeleitet.|  
|`_MYFORMS`|Aktiviert `My.Forms`, wenn die Konstante `TRUE` ist.|  
|`_MYUSERTYPE`|Aktiviert `My.User`, wenn die Konstante den Wert "Web" oder "Windows" aufweist:<br /><br /> -   Die "Web"\-Version von `My.User` ist der Benutzeridentität der aktuellen HTTP\-Anforderung zugeordnet.<br />-   Die "Windows"\-Version von `My.User` ist dem aktuellen Prinzipal des Threads zugeordnet.|  
|`_MYWEBSERVICES`|Aktiviert `My.WebServices`, wenn die Konstante `TRUE` ist.|  
|`_MYTYPE`|Aktiviert `My.Log`, `My.Request`, und `My.Response`, wenn die Konstante den Wert "Web" aufweist.|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.Logging.Log>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)   
 [My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)   
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)