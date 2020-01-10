---
title: Verwenden von Standardausnahmetypen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708983"
---
# <a name="using-standard-exception-types"></a>Verwenden von Standardausnahmetypen
In diesem Abschnitt werden die Standard Ausnahmen, die vom Framework bereitgestellt werden, und die Details ihrer Verwendung beschrieben. Die Liste ist keineswegs vollständig. Weitere Informationen zur Verwendung von frameworkausnahmetypen finden Sie in der .NET Framework Referenz Dokumentation.  
  
## <a name="exception-and-systemexception"></a>Exception und SystemException  
 **X DO NOT** auslösen <xref:System.Exception?displayProperty=nameWithType> oder <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` oder `System.SystemException` in Frameworkcode, es sei denn, Sie erneut auslösen möchten.  
  
 **X AVOID** abfangen `System.Exception` oder `System.SystemException`, außer bei Ausnahmehandler der obersten Ebene.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** lösen oder eine Ableitung von <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** Auslösen einer <xref:System.InvalidOperationException> , wenn das Objekt in einem unzulässigen Zustand ist.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>Argumumtexception, ArgumentNullException und argumentoudefrangeexception  
 **✓ DO** auslösen <xref:System.ArgumentException> oder einem seiner Untertypen, wenn ungültige Argumente auf einen Member übergeben werden. Bevorzugen Sie ggf. den am weitesten abgeleiteten Ausnahmetyp.  
  
 **✓ DO** legen Sie die `ParamName` Eigenschaft, die beim Auslösen einer die Unterklasse von `ArgumentException`.  
  
 Diese Eigenschaft stellt den Namen des Parameters dar, der bewirkt hat, dass die Ausnahme ausgelöst wurde. Beachten Sie, dass die-Eigenschaft mit einer der-Konstruktorüberladungen festgelegt werden kann.  
  
 **✓ DO** verwenden `value` für den Namen des Parameters impliziter Wert der Eigenschaftensetter.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, indexouesfrangeexception und AccessViolationException  
 **X DO NOT** ermöglichen öffentlich aufrufbare APIs explizit oder implizit auslöst <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, oder <xref:System.IndexOutOfRangeException>. Diese Ausnahmen sind von der Ausführungs-Engine reserviert und werden ausgelöst und weisen in den meisten Fällen auf einen Fehler hin.  
  
 Argument Überprüfung, um das Auslösen dieser Ausnahmen zu vermeiden. Wenn Sie diese Ausnahmen auslösen, werden Implementierungsdetails der Methode angezeigt, die sich im Laufe der Zeit ändern können.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** explizit auslösen <xref:System.StackOverflowException>. Die Ausnahme sollte explizit nur durch die CLR ausgelöst werden.  
  
 **X DO NOT** catch `StackOverflowException`.  
  
 Es ist beinahe unmöglich, verwalteten Code zu schreiben, der bei der Anwesenheit beliebiger Stapel Überläufe konsistent bleibt. Die nicht verwalteten Teile der CLR bleiben konsistent, indem Sie die Stapel Überläufe mithilfe von Tests an klar definierte Orte verschieben, anstatt Sie aus willkürlichen Stapel Überläufen zu sichern.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** explizit auslösen <xref:System.OutOfMemoryException>. Diese Ausnahme wird nur durch die CLR-Infrastruktur ausgelöst.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, Seh Exception und ExecutionEngineException  
 **X DO NOT** explizit auslösen <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, und <xref:System.Runtime.InteropServices.SEHException>. Diese Ausnahmen müssen nur von der CLR-Infrastruktur ausgelöst werden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
