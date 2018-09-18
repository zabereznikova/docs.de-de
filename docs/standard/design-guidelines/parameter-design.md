---
title: Parameterentwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964815"
---
# <a name="parameter-design"></a>Parameterentwurf
Dieser Abschnitt enthält allgemeine Richtlinien zum parameterentwurf, einschließlich der Abschnitte mit Richtlinien für die Überprüfung der Argumente. Darüber hinaus, lesen Sie die Hinweise in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ DO** verwenden, der am wenigsten abgeleiteten Parametertyp, die die Funktionen für das Element bereitstellt.  
  
 Nehmen wir beispielsweise an, dass eine Methode zu entwerfen, die Listet eine Auflistung, und jedes Element in der Konsole ausgegeben, werden soll. Eine solche Methode dauert <xref:System.Collections.IEnumerable> als Parameter nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>, z. B.  
  
 **X DO NOT** reservierte Parameter verwenden.  
  
 Wenn mehr Eingabe, um ein Element in einer künftigen Version erforderlich ist, kann eine neue Überladung hinzugefügt werden.  
  
 **X DO NOT** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.  
  
 Zeiger und mehrdimensionale Arrays sind relativ schwierig, ordnungsgemäß zu verwenden. In fast allen Fällen können APIs überarbeitet werden, um zu vermeiden, nehmen diese Typen als Parameter.  
  
 **✓ DO** platzieren Sie alle `out` Parameter, die alle per-Wert und `ref` Parameter (ausgenommen Parameterarrays), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt (finden Sie unter [Member Überladen von](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 Die `out` Parameter können als zusätzliche Werte angezeigt werden, und gruppieren sie die Signatur der Methode ist einfacher zu verstehen.  
  
 **✓ DO** benennen Parameter aus, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.  
  
 Dies besser wird die Beziehung zwischen den Methoden kommuniziert.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>Auswählen zwischen für Enumerationen und booleschen Parametern  
 **✓ DO** Enumerationen verwenden, wenn ein Element mindestens zwei boolesche Parameter hätten.  
  
 **X DO NOT** boolesche Werte verwenden, es sei denn, Sie absolut sicher, dass es werden nie mehr als zwei Werte erforderlich sind.  
  
 Enumerationen bieten Ihnen etwas Platz für zukünftige Hinzufügen von Werten, aber Sie sollten über alle Auswirkungen auf die Enumerationen, die in beschriebenen Werte hinzufügen [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ CONSIDER** mit boolesche Werte für Konstruktorparameter, die tatsächlich zwei-Status-Werte sind und zur Initialisierung von boolescher Eigenschaften, die einfach verwendet werden.  
  
### <a name="validating-arguments"></a>Überprüfen von Argumenten  
 **✓ DO** weitergegebenen Argumenten um öffentlich, geschützt oder explizit implementierten Member zu überprüfen. Löst <xref:System.ArgumentException?displayProperty=nameWithType>, oder eine ihrer Unterklassen, wenn die Validierung fehlschlägt.  
  
 Beachten Sie, dass die tatsächliche Validierung nicht unbedingt in der öffentlichen oder geschützten Member selbst nicht geschehen. Dies kann auf einer niedrigeren Ebene in eine private oder interne Routine eintreten. Der wichtigste Aspekt ist, überprüft die Argumente, die gesamte Oberfläche, die an die Endbenutzer verfügbar gemacht wird.  
  
 **✓ DO** auslösen <xref:System.ArgumentNullException> Wenn ein null-Argument übergeben wird und das Element keine null-Argumente unterstützt.  
  
 **✓ DO** Enum-Parameter überprüft.  
  
 Führen Sie Sie nicht davon gehen Sie aus, dass Enum-Argumente in den Bereich, der von der Enumeration definiert ist. Die CLR ermöglicht, einen beliebigen ganzzahligen Wert in einen Enum-Wert umwandeln, selbst wenn der Wert nicht in die Enumeration definiert ist.  
  
 **X DO NOT** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Enum Bereich überprüft.  
  
 **✓ DO** Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem sie überprüft wurden.  
  
 Wenn der Member sicherheitsrelevant ist, werden Sie aufgefordert, erstellen Sie eine Kopie, und klicken Sie dann überprüfen und verarbeiten das Argument.  
  
### <a name="parameter-passing"></a>Parameterübergabe  
 Aus der Perspektive einer Framework-Designer, es gibt drei Hauptgruppen von Parametern: per-Wert-Parametern `ref` Parameter und `out` Parameter.  
  
 Wenn ein Argument über einen Parameter nach Wert übergeben wird, erhält das Element eine Kopie des tatsächlichen Arguments übergeben. Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt. Am häufigsten verwendete CLR-Sprachen wie c#, VB.NET und C++-Standard zum Übergeben von Parametern als Wert.  
  
 Wenn ein Argument übergeben wird, über eine `ref` Parameter, der Mitglied erhält einen Verweis auf das tatsächliche Argument übergeben. Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird ein Verweis auf den Verweis auf dem Stapel abgelegt. `Ref` Parameter können verwendet werden, um das Element zu ändern, vom Aufrufer übergegebene Argumente machen.  
  
 `Out` Parameter sind ähnlich, `ref` Parameter, mit einigen kleinen unterschieden. Der Parameter wird anfänglich betrachtet, nicht zugewiesen und kann nicht in den Text des Elements gelesen werden, bevor ihr einen Wert zugewiesen wird. Darüber hinaus muss der Parameter einen Wert zugewiesen werden, bevor das Element zurückgibt.  
  
 **X AVOID** mit `out` oder `ref` Parameter.  
  
 Mithilfe von `out` oder `ref` Parameter erfordert Erfahrung mit Zeigern, Kenntnisse der Unterschiede zwischen Werttypen und Verweistypen und Umgang mit Methoden mit mehreren Rückgabewerten. Außerdem ist der Unterschied zwischen `out` und `ref` Parameter kann häufig nicht interpretiert werden. Framework-Architekten Entwerfen für eine Breite Zielgruppe sollten nicht erwarten, dass der Benutzer das master arbeiten mit `out` oder `ref` Parameter.  
  
 **X DO NOT** Verweistypen als Verweis übergeben.  
  
 Es gibt einige wenige Ausnahmen für die Regel, wie z. B. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.  
  
### <a name="members-with-variable-number-of-parameters"></a>Elemente mit einer Variablen Anzahl von Parametern  
 Elemente, die eine Variable Anzahl von Argumenten akzeptieren können, werden durch die Bereitstellung eines Arrayparameter ausgedrückt. Z. B. <xref:System.String> bietet die folgende Methode:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Ein Benutzer kann dann Aufrufen der <xref:System.String.Format%2A?displayProperty=nameWithType> -Methode wie folgt:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Durch Hinzufügen des C#-Params-Schlüsselworts auf einen Arrayparameter ändert der Parameter auf einen Arrayparameter so genannte Params und verfügt über eine Tastenkombination für das ein temporäres Array erstellen.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Auf diese Weise kann der Benutzer zum Aufrufen der Methode durch die Elemente des Arrays in der Argumentliste direkt übergeben.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Beachten Sie, dass das Params-Schlüsselwort nur der letzte Parameter in der Liste hinzugefügt werden kann.  
  
 **✓ CONSIDER** Arrayparameter des Params-Schlüsselworts hinzugefügt, wenn Sie davon ausgehen, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass. Erwartet werden, dass viele der Elemente in gängigen Szenarien übergeben werden, Benutzer übergibt diese Elemente Inline wahrscheinlich nicht ohnehin, und das Params-Schlüsselwort ist daher nicht erforderlich.  
  
 **X AVOID** Params-Arrays verwenden, wenn ein Aufrufer fast immer die Eingabe bereits in einem Array würde.  
  
 Mitglieder mit Arrayparametern Byte würde z. B. durch Übergeben der einzelnen Bytes fast nie aufgerufen werden. Aus diesem Grund verwenden Byte-Array-Parameter in .NET Framework nicht das Params-Schlüsselwort.  
  
 **X DO NOT** Params-Arrays verwenden, wenn das Array vom dauert des Params-Array Parameters-Element geändert wird.  
  
 Aufgrund der Tatsache, dass viele Compiler die Argumente für das Element in ein temporäres Array an der Aufrufsite umwandeln das Array kann kein temporäres Objekt sein, und somit keine Änderungen an das Array verloren.  
  
 **✓ CONSIDER** des Params-Schlüsselworts in einer einfachen Überladung verwenden, auch wenn eine komplexere Überladung, konnte ihn nicht verwenden.  
  
 Fragen Sie sich, wenn Benutzer in einer Überladung der Parameterarray müssen, auch wenn es in alle Überladungen war nicht Wert würde.  
  
 **✓ DO** versuchen, Order-Parameter, und es Ihnen ermöglicht mithilfe des Params-Schlüsselworts.  
  
 **✓ CONSIDER** spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in extrem leistungsabhängigen-APIs bereitstellen.  
  
 Dadurch kann vermieden werden Array von Objekten erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird. Bilden Sie die Namen der Parameter, indem ein einzelnes Format des Array-Parameters und ein numerisches Suffix hinzugefügt.  
  
 Sie sollten dies nur tun, wenn Sie beabsichtigen, der Pfad für den gesamten besondere Schreibweisen, nicht nur ein Array erstellen, und rufen Sie die allgemeine Methode.  
  
 **✓ DO** Beachten Sie, dass Null kann als ein Params-Argument übergeben werden.  
  
 Sie sollten überprüfen, dass das Array nicht vor der Verarbeitung null ist.  
  
 **X DO NOT** verwenden die `varargs` Methoden, sogenannten mit den Auslassungspunkten.  
  
 Einige CLR-Sprachen, z. B. C++, unterstützen eine alternative Konvention für die Übergabe von Variablen Parameterlisten namens `varargs` Methoden. Die Konvention sollte nicht in Frameworks verwendet werden, da es nicht CLS-kompatibel ist.  
  
### <a name="pointer-parameters"></a>Zeigerparameter  
 Im Allgemeinen Zeiger nicht in die öffentliche Oberfläche eines Frameworks gut entworfene von verwaltetem Code angezeigt werden soll. In den meisten Fällen, sollte als Zeiger gekapselt werden. Jedoch in einigen Fällen Zeiger aus Gründen der Interoperabilität erforderlich sind, und Verwenden von Zeigern in solchen Fällen eignet.  
  
 **✓ DO** bieten eine Alternative für ein Element, das ein Zeigerargument akzeptiert, da Zeiger nicht CLS-kompatibel sind.  
  
 **X AVOID** auf diese Weise die aufwändige Prüfung von Zeigerargumente Argument.  
  
 **✓ DO** Konventionen gemeinsamen Zeiger-bezogene beim Entwerfen der Member mit Zeigern.  
  
 Beispielsweise besteht keine Notwendigkeit, übergeben den Startindex, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
