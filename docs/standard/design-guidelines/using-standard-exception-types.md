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
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743540"
---
# <a name="using-standard-exception-types"></a>Verwenden von Standardausnahmetypen
In diesem Abschnitt werden die Standard Ausnahmen, die vom Framework bereitgestellt werden, und die Details ihrer Verwendung beschrieben. Die Liste ist keineswegs vollständig. Weitere Informationen zur Verwendung von frameworkausnahmetypen finden Sie in der .NET Framework Referenz Dokumentation.

## <a name="exception-and-systemexception"></a>Exception und SystemException
 ❌ keine <xref:System.Exception?displayProperty=nameWithType> oder <xref:System.SystemException?displayProperty=nameWithType>auslösen.

 ❌ können keine `System.Exception` oder `System.SystemException` im Frameworkcode erfassen, es sei denn, Sie beabsichtigen, Sie erneut auszulösen.

 ❌ vermeiden Sie das Abfangen von `System.Exception` oder `System.SystemException`, außer in Ausnahme Handlern der obersten Ebene.

## <a name="applicationexception"></a>ApplicationException
 ❌ die <xref:System.ApplicationException>nicht auslösen oder ableiten.

## <a name="invalidoperationexception"></a>InvalidOperationException
 ✔️ eine <xref:System.InvalidOperationException> auslösen, wenn sich das Objekt in einem unzulässigen Zustand befindet.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>Argumumtexception, ArgumentNullException und argumentoudefrangeexception
 ✔️ lösen <xref:System.ArgumentException> oder einen seiner Untertypen aus, wenn ungültige Argumente an einen Member übergeben werden. Bevorzugen Sie ggf. den am weitesten abgeleiteten Ausnahmetyp.

 ✔️ Legen Sie die `ParamName`-Eigenschaft fest, wenn Sie eine der Unterklassen von `ArgumentException`auslösen.

 Diese Eigenschaft stellt den Namen des Parameters dar, der bewirkt hat, dass die Ausnahme ausgelöst wurde. Beachten Sie, dass die-Eigenschaft mit einer der-Konstruktorüberladungen festgelegt werden kann.

 ✔️ Verwenden Sie `value` für den Namen des impliziten value-Parameters von Eigenschaften Settern.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, indexouesfrangeexception und AccessViolationException
 ❌ erlauben Sie nicht, öffentlich aufrufbare APIs explizit oder implizit <xref:System.NullReferenceException>, <xref:System.AccessViolationException>oder <xref:System.IndexOutOfRangeException>auszulösen. Diese Ausnahmen sind von der Ausführungs-Engine reserviert und werden ausgelöst und weisen in den meisten Fällen auf einen Fehler hin.

 Argument Überprüfung, um das Auslösen dieser Ausnahmen zu vermeiden. Wenn Sie diese Ausnahmen auslösen, werden Implementierungsdetails der Methode angezeigt, die sich im Laufe der Zeit ändern können.

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌ nicht explizit <xref:System.StackOverflowException>auslösen. Die Ausnahme sollte explizit nur durch die CLR ausgelöst werden.

 ❌ `StackOverflowException`nicht auffangen.

 Es ist beinahe unmöglich, verwalteten Code zu schreiben, der bei der Anwesenheit beliebiger Stapel Überläufe konsistent bleibt. Die nicht verwalteten Teile der CLR bleiben konsistent, indem Sie die Stapel Überläufe mithilfe von Tests an klar definierte Orte verschieben, anstatt Sie aus willkürlichen Stapel Überläufen zu sichern.

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌ nicht explizit <xref:System.OutOfMemoryException>auslösen. Diese Ausnahme wird nur durch die CLR-Infrastruktur ausgelöst.

## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, Seh Exception und ExecutionEngineException
 ❌ <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>und <xref:System.Runtime.InteropServices.SEHException>nicht explizit auslösen. Diese Ausnahmen müssen nur von der CLR-Infrastruktur ausgelöst werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
