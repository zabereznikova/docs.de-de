---
title: Dispose-Muster
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: KrzysztofCwalina
ms.openlocfilehash: ee6e9898ae93e2e6628eadec150a3c9c05f5d9c5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147711"
---
# <a name="dispose-pattern"></a>Dispose-Muster
Alle Programme rufen eine oder mehrere Systemressourcen, z. B. Arbeitsspeicher, Systemhandles oder Datenbankverbindungen, im Verlauf ihrer Ausführung. Entwickler müssen Sie vorsichtig, wenn eine solche Systemressourcen belegen, da diese freigegeben werden müssen, nachdem sie abgerufen und verwendet wurden.  
  
 Die CLR bietet Unterstützung für automatische Speicherverwaltung. Verwalteter Speicher (Speichermenge, die mit dem c#-Operator `new`) muss nicht explizit freigegeben werden. Es wird automatisch vom Garbage Collector (GC) freigegeben. Dadurch kann Entwickler von der Aufgabe mühsam und schwierig, der Freigabe von Speicher und wurde einer der Hauptgründe, warum die noch nie dagewesene Produktivität von .NET Framework möglich war.  
  
 Leider ist nur eine von vielen Arten von Systemressourcen, verwalteter Speicher. Ressourcen mit Ausnahme des verwalteten Speichers ist weiterhin explizit freigegeben werden müssen und als nicht verwaltete Ressourcen bezeichnet werden. Der Garbage Collector insbesondere OTKLoadr können keine solche nicht verwalteten Ressourcen verwalten was bedeutet, dass die Verantwortung für die Verwaltung von nicht verwalteten Ressourcen in die Hände der Entwickler liegt.  
  
 Die CLR bietet Hilfe bei der Freigabe von nicht verwalteter Ressourcen. <xref:System.Object?displayProperty=nameWithType> deklariert eine virtuelle Methode <xref:System.Object.Finalize%2A> (auch als Finalizer bezeichnet), wird von der Garbage Collector aufgerufen, bevor der Speicher des Objekts von der Garbage Collector freigegeben wird, und überschrieben werden, kann um nicht verwaltete Ressourcen freizugeben. Typen, die den Finalizer überschreiben werden als beendbare Typen bezeichnet.  
  
 Auch wenn Finalizer in einigen Szenarien für die Bereinigung gelten, haben sie zwei bedeutende Nachteile:  
  
-   Der Finalizer wird aufgerufen, wenn die GC erkennt, dass ein Objekt für die Auflistung. Dies erfolgt auf einige unbestimmten Zeitraum nach die Ressource nicht mehr benötigt wird. Die Verzögerung zwischen den bei der Entwickler kann, oder möchten Version der Ressource und die Uhrzeit, wann die Ressource tatsächlich vom Finalizer freigegeben wird, ist möglicherweise nicht akzeptabel in Programmen, die viele knappe Ressourcen (Ressourcen, die einfach überlastet werden können) abrufen oder in Fälle, in denen Ressourcen zu verwenden (z. B. großen nicht verwalteten Speicherpuffer) teuer sind.  
  
-   Wenn die CLR einen Finalizer aufrufen muss, muss diese Sammlung von der Speicher des Objekts verschieben, bis die nächste runden der Garbagecollection (die Finalizer, der zwischen Auflistungen ausgeführt wird). Dies bedeutet, dass der Speicher des Objekts (und alle Objekte, auf die, denen er verweist) nicht für einen längeren Zeitraum ist.  
  
 Aus diesem Grund der vertrauenden Seite ausschließlich auf Finalizer möglicherweise nicht geeignet, in vielen Szenarien, wenn es darauf ankommt, nicht verwaltete Ressourcen so schnell wie möglich freizugeben, beim Umgang mit knappe Ressourcen oder in einer hoch leistungsfähigen Szenarien, in denen die hinzugefügten GC-Overhead ist der Beendigung nicht zulässig.  
  
 Das Framework bietet die <xref:System.IDisposable?displayProperty=nameWithType> -Schnittstelle, die implementiert werden sollte, um den Entwickler bereitzustellen, eine manuelle Möglichkeit, die nicht verwaltete Ressourcen freizugeben, sobald sie nicht benötigt werden. Außerdem wird die <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> -Methode, die der Garbage Collector, die Sie informieren kann ein Objekt wurde manuell wieder entfernt, und muss nicht mehr beendet werden in diesem Fall kann der Arbeitsspeicher des Objekts zuvor freigegeben werden. Typen implementiert die `IDisposable` Schnittstelle werden als Verwerfbare Typen bezeichnet.  
  
 Das Dispose-Muster richtet sich an, die Nutzung und die Implementierung von Finalizern zu standardisieren und die `IDisposable` Schnittstelle.  
  
 Das Hauptargument für das Muster zur Reduzierung der Komplexität der Implementierung ist die <xref:System.Object.Finalize%2A> und <xref:System.IDisposable.Dispose%2A> Methoden. Die Komplexität rührt daher, dass die Methoden einige, aber nicht alle Codepfade aufweisen (die Unterschiede werden später in diesem Kapitel beschrieben). Darüber hinaus stehen aus historische Gründen für einige Elemente des Musters im Zusammenhang mit der Entwicklung der sprachunterstützung für deterministisch ressourcenverwaltung.  
  
 **✓ DO** das grundlegende Dispose-Muster für Typen, die Instanzen von Verwerfbare Typen implementieren. Finden Sie unter den [grundlegende Dispose-Muster](#basic_pattern) finden Sie Details für das grundlegende Muster.  
  
 Wenn ein Typ für die Lebensdauer der andere verwerfbare Objekte verantwortlich ist, benötigen Entwickler eine Möglichkeit, diese zu löschen. Mithilfe des Containers `Dispose` Methode ist eine bequeme Möglichkeit, dies zu ermöglichen.  
  
 **✓ DO** grundlegende Dispose-Muster implementiert wird und einen Finalizer bereitstellen, auf Ressourcen, die explizit freigegeben werden müssen und die keine Finalizer.  
  
 Beispielsweise sollte das Muster für Typen, die Speichern von nicht verwalteten Arbeitsspeicher implementiert werden. Die [beendbare Typen](#finalizable_types) Abschnitt wird erläutert, Richtlinien, die im Zusammenhang mit der Implementierung von Finalizern.  
  
 **· ERWÄGEN SIE** die Implementierung des grundlegenden Dispose-Musters bei Klassen, die selbst keine verwalteten Ressourcen oder verwerfbaren Objekte enthalten, aber Untertypen umfassen können, die dies tun.  
  
 Ein hervorragendes Beispiel dafür ist die <xref:System.IO.Stream?displayProperty=nameWithType> -Klasse. Während es sich hierbei um eine abstrakte Basisklasse handelt, die keinerlei Ressourcen enthält, tun dies die meisten ihrer Unterklassen. Aus diesem Grund implementiert sie das Dispose-Muster.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Grundlegende Dispose-Muster  
 Umfasst auch die grundlegende Implementierung des Musters die Implementierung der `System.IDisposable` -Schnittstelle, und deklarieren die `Dispose(bool)` Methode, die alle Ressourcen der Bereinigungslogik, gemeinsam genutzt werden implementiert die `Dispose` -Methode und der optionalen Finalizer.  
  
 Das folgende Beispiel zeigt eine einfache Implementierung von das grundlegende Muster:  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 Der boolesche Parameter `disposing` gibt an, ob die Methode aufgerufen wurde, aus der `IDisposable.Dispose` Implementierung oder vom Finalizer. Die `Dispose(bool)` Implementierung sollte überprüfen Sie den Parameter vor dem Zugriff auf andere Verweisobjekte (z. B. das Ressourcenfeld im vorhergehenden Beispiel). Solche Objekte sollte nur zugegriffen werden, wenn die Methode aufgerufen wird die `IDisposable.Dispose` Implementierung (wenn die `disposing` -Parameter ist gleich "true"). Wenn die Methode vom Finalizer aufgerufen wird (`disposing` ist "false"), andere Objekte sollten nicht zugegriffen werden. Der Grund ist, dass Objekte in unvorhersehbarer Reihenfolge abgeschlossen werden und daher diese oder eine ihrer Abhängigkeiten, möglicherweise bereits abgeschlossen.  
  
 In diesem Abschnitt gilt auch, Klassen, die mit einer Basis, die nicht bereits das Dispose-Muster implementiert. Wenn Sie von einer Klasse erben, bereits das Steuerelementmuster implementiert, einfach außer Kraft setzen der `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.  
  
 **✓ DO** deklarieren eine `protected virtual void Dispose(bool disposing)` Methode, um die gesamte Logik zu zentralisieren, die sich auf die Freigabe nicht verwalteter Ressourcen beziehen.  
  
 Bei dieser Methode sollte die ressourcenbereinigung aller auftreten. Die Methode wird von beiden die Finalizer aufgerufen und die `IDisposable.Dispose` Methode. Der Parameter werden als false, wenn in einem Finalizer aufgerufen wird. Es sollte verwendet werden, um sicherzustellen, dass jeder Code ausgeführt wird, während des Abschlusses keine andere finalisierbare Objekte zugreift. Details der Implementierung von Finalizern werden im nächsten Abschnitt beschrieben.  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ DO** implementieren die `IDisposable` Schnittstelle durch den Aufruf einfach `Dispose(true)` gefolgt von `GC.SuppressFinalize(this)`.  
  
 Der Aufruf von `SuppressFinalize` sollte nur auftreten, wenn `Dispose(true)` erfolgreich ausgeführt wird.  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X DO NOT** stellen die parameterlose `Dispose` virtuelle Methode.  
  
 Die `Dispose(bool)` Methode ist diejenige, die von Unterklassen überschrieben werden sollen.  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 **X DO NOT** alle Überladungen der deklarieren die `Dispose` andere Methode als `Dispose()` und `Dispose(bool)`.  
  
 `Dispose` Berücksichtigen Sie können dieses Muster festzuschreiben und schließt Verwechslungen zwischen Implementierungen, Benutzer und dem Compiler ein reserviertes Wort. Bei einigen Sprachen können auch dieses Muster für bestimmte Typen automatisch zu implementieren.  
  
 **✓ DO** ermöglichen die `Dispose(bool)` Methode, die mehr als einmal aufgerufen werden. Die Methode kann auch nach dem ersten Aufruf sind keine weiteren Aktionen.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X AVOID** Auslösen einer Ausnahme heraus `Dispose(bool)` außer in kritischen Situationen, in denen der enthaltende Prozess wurde beschädigt (Speicherverlusten, inkonsistent Freigabezustand usw..).  
  
 Benutzer erwarten, dass ein Aufruf von `Dispose` wird keine Ausnahme ausgelöst.  
  
 Wenn `Dispose` eine Ausnahme auslösen konnte, weitere Bereinigungslogik von finally-Block wird nicht ausgeführt. Um dieses Problem umgehen, muss der Benutzer würde für jeden Aufruf umschließen `Dispose` (innerhalb der finally-block!) in einem Try-Block, was zu sehr komplexen Cleanup-Handler führt. Wenn die Ausführung einer `Dispose(bool disposing)` Methode nie lösen eine Ausnahme aus, wenn der disposing "false" ist. Auf diese Weise wird den Prozess beendet, wenn in einem Finalizer-Kontext ausgeführt.  
  
 **✓ DO** Auslösen einer <xref:System.ObjectDisposedException> über ein Element, das verwendet werden kann, nachdem das Objekt verworfen wurde.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ CONSIDER** als Methode `Close()`, zusätzlich zu den `Dispose()`, wenn schließen standard Terminologie im Bereich ist.  
  
 Dabei ist es wichtig, dass Sie machen die `Close` Implementierung ist identisch mit `Dispose` und implementieren Sie die `IDisposable.Dispose` Methode explizit.  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a>Beendbare Typen  
 Beendbare Typen sind Typen, die das grundlegende Dispose-Muster zu erweitern, indem Sie den Finalizer überschreiben und die Bereitstellung Beendigungscodepfad in die `Dispose(bool)` Methode.  
  
 Finalizer sind bekanntermaßen schwierig zu richtig zu implementieren, in erster Linie verwendet werden, da Sie bestimmte (normalerweise gültigen) Annahmen über den Zustand des Systems während der Ausführung vornehmen können. Die folgenden Richtlinien sollten sorgfältig berücksichtigt werden.  
  
 Beachten Sie, dass einige der Richtlinien nicht nur auf gelten die `Finalize` -Methode, jedoch keinen Code von einem Finalizer aufgerufen. Im Fall von grundlegenden Dispose zuvor definierten Muster, die Logik, die in ausgeführt wird daher `Dispose(bool disposing)` bei der `disposing` Parameter ist "false".  
  
 Wenn die Basisklasse der Klasse bereits finalisierbaren und das grundlegende Dispose-Muster implementiert, sollten Sie nicht überschreiben `Finalize` erneut aus. Sie sollten stattdessen nur überschreiben, die `Dispose(bool)` Methode, um zusätzliche Ressourcen Bereinigungslogik bereitzustellen.  
  
 Der folgende Code zeigt ein Beispiel für eine Art beendbare:  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X AVOID** Typen finalisierbaren vornehmen.  
  
 Überlegen Sie allen Fällen, in denen Sie glauben, dass es sich bei ein Finalizer erforderlich ist. Es ist eine echte Kosten im Zusammenhang mit Instanzen mit Finalizer, aus der Perspektive für eine Leistung und den Code Komplexität. Bevorzugen, wie z. B. Verwenden von Ressourcen-Wrappern <xref:System.Runtime.InteropServices.SafeHandle> zum nicht verwaltete Ressourcen zu kapseln, wenn möglich, in diesem Fall ein Finalizer wird nicht erforderlich, da der Wrapper für die ressourcenbereinigung der eigenen zuständig ist.  
  
 **X DO NOT** Werttypen finalisierbaren vornehmen.  
  
 Nur Verweistypen erhalten tatsächlich von der CLR beendet, und somit jeder Versuch, platzieren Sie einen Finalizer für einen Werttyp ignoriert werden. Die C#- und C++-Compiler erzwingen diese Regel.  
  
 **✓ DO** stellen einen Typ finalisierbaren, wenn der Typ verantwortlich ist für eine nicht verwaltete Ressource, die über keinen eigenen Finalizer freigeben.  
  
 Wenn den Finalizer zu implementieren, rufen Sie einfach `Dispose(false)` und platzieren Sie Bereinigungslogik für alle Ressourcen innerhalb der `Dispose(bool disposing)` Methode.  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 **✓ DO** das grundlegende Dispose-Muster für jede finalisierbaren Typ zu implementieren.  
  
 Dadurch kann Benutzer des Typs eine deterministische Bereinigung der diese Ressourcen explizit führen Sie für die der Finalizer zuständig ist.  
  
 **X DO NOT** finalisierbare Objekte in der Finalizer-Codepfad zugegriffen werden, da ist es bedeutendes Risiko, dass sie bereits finalisiert sein werden.  
  
 Beispielsweise ein abzuschließendes Objekt ein, die einen Verweis auf einen anderen abzuschließendes Objekt B kann nicht zuverlässig verwenden B in der ein Finalizer, oder umgekehrt. Finalizer werden in zufälliger Reihenfolge (eine schwache Reihenfolgegarantien zusammen für kritische Finalisierung) aufgerufen.  
  
 Bedenken Sie außerdem, dass Objekte in statischen Variablen gespeichert an bestimmten Punkten bei einer Anwendung entladen der Domäne oder beim Beenden des Prozesses erfasst werden. Zugreifen auf eine statische Variable, die bezieht sich auf ein abzuschließendes Objekt (oder einen Aufruf einer statischen Methode, die in statischen Variablen gespeicherten Werte verwenden kann) möglicherweise nicht sicher If <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> "Wahr" zurückgegeben.  
  
 **✓ DO** stellen Ihre `Finalize` geschützte Methode.  
  
 C#, C++ und VB.NET-Entwickler müssen nicht, kümmern, da der Compiler helfen, um diese Richtlinie zu erzwingen.  
  
 **X DO NOT** können Ausnahmen Escapezeichen aus der Finalizer-Logik, mit Ausnahme von System kritische Fehler.  
  
 Wenn von einem Finalizer eine Ausnahme ausgelöst wird, wird die CLR heruntergefahren, der gesamte Prozess (ab .NET Framework Version 2.0) ausführen und die Ressourcen auf kontrollierte Weise Freigabe anderer Finalizer verhindert.  
  
 **✓ CONSIDER** erstellen und verwenden ein abzuschließendes Objekt inaktiv kritische (ein Typ mit einer Typhierarchie, die enthält <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) für Situationen, in der ein Finalizer absolut werden auch bei der erzwungenen Anwendung Domäne entladen und Threads ausgeführt muss, Bricht ab.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
