---
title: Verwenden von Standardausnahmetypen
description: Informieren Sie sich über Standard Ausnahme Typen in .net. Erfahren Sie mehr über "SystemException", "ApplicationException", "argumumtexception", "COMException" und mehr.
ms.date: 10/22/2008
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: ef420d47e6204aef5e3d9bc12ace31fbf5521ee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734360"
---
# <a name="using-standard-exception-types"></a>Verwenden von Standardausnahmetypen

In diesem Abschnitt werden die Standard Ausnahmen, die vom Framework bereitgestellt werden, und die Details ihrer Verwendung beschrieben. Die Liste ist keineswegs vollständig. Weitere Informationen zur Verwendung von frameworkausnahmetypen finden Sie in der .NET Framework Referenz Dokumentation.

## <a name="exception-and-systemexception"></a>Exception und SystemException

 ❌ Lösen Sie nicht <xref:System.Exception?displayProperty=nameWithType> oder aus <xref:System.SystemException?displayProperty=nameWithType> .

 ❌ Fangen `System.Exception` Sie oder nicht `System.SystemException` im Frameworkcode ab, es sei denn, Sie möchten erneut auslösen.

 ❌ Vermeiden Sie das Abfangen von `System.Exception` oder `System.SystemException` , außer in Ausnahme Handlern der obersten Ebene.

## <a name="applicationexception"></a>ApplicationException

 ❌ Lösen Sie nicht aus oder leiten Sie von ab <xref:System.ApplicationException> .

## <a name="invalidoperationexception"></a>InvalidOperationException

 ✔️ lösen eine <xref:System.InvalidOperationException> aus, wenn sich das Objekt in einem unzulässigen Zustand befindet.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>Argumumtexception, ArgumentNullException und argumentoudefrangeexception

 ✔️ Throw <xref:System.ArgumentException> oder einen seiner Untertypen aus, wenn ungültige Argumente an einen Member übergeben werden. Bevorzugen Sie ggf. den am weitesten abgeleiteten Ausnahmetyp.

 ✔️ die-Eigenschaft festlegen, `ParamName` Wenn eine der Unterklassen von ausgelöst wird `ArgumentException` .

 Diese Eigenschaft stellt den Namen des Parameters dar, der bewirkt hat, dass die Ausnahme ausgelöst wurde. Beachten Sie, dass die-Eigenschaft mit einer der-Konstruktorüberladungen festgelegt werden kann.

 ✔️ Verwenden Sie `value` für den Namen des impliziten value-Parameters von Eigenschaften Settern.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, indexouesfrangeexception und AccessViolationException

 ❌ Lassen Sie nicht zu, dass öffentlich Aufruf Bare APIs, oder explizit oder implizit auslösen <xref:System.NullReferenceException> <xref:System.AccessViolationException> <xref:System.IndexOutOfRangeException> . Diese Ausnahmen sind von der Ausführungs-Engine reserviert und werden ausgelöst und weisen in den meisten Fällen auf einen Fehler hin.

 Argument Überprüfung, um das Auslösen dieser Ausnahmen zu vermeiden. Wenn Sie diese Ausnahmen auslösen, werden Implementierungsdetails der Methode angezeigt, die sich im Laufe der Zeit ändern können.

## <a name="stackoverflowexception"></a>StackOverflowException

 ❌ Nicht explizit auslösen <xref:System.StackOverflowException> . Die Ausnahme sollte explizit nur durch die CLR ausgelöst werden.

 ❌ Nicht abfangen `StackOverflowException` .

 Es ist beinahe unmöglich, verwalteten Code zu schreiben, der bei der Anwesenheit beliebiger Stapel Überläufe konsistent bleibt. Die nicht verwalteten Teile der CLR bleiben konsistent, indem Sie die Stapel Überläufe mithilfe von Tests an klar definierte Orte verschieben, anstatt Sie aus willkürlichen Stapel Überläufen zu sichern.

## <a name="outofmemoryexception"></a>OutOfMemoryException

 ❌ Nicht explizit auslösen <xref:System.OutOfMemoryException> . Diese Ausnahme wird nur durch die CLR-Infrastruktur ausgelöst.

## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, Seh Exception und ExecutionEngineException

 ❌ Lösen Sie, und nicht explizit aus <xref:System.Runtime.InteropServices.COMException>  <xref:System.ExecutionEngineException> <xref:System.Runtime.InteropServices.SEHException> . Diese Ausnahmen müssen nur von der CLR-Infrastruktur ausgelöst werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwurfsrichtlinien für Ausnahmen](exceptions.md)
