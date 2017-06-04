---
title: "reentrancy MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "unmanaged code, debugging"
  - "transitioning threads unmanaged to managed code"
  - "reentrancy MDA"
  - "reentrancy without an orderly transition"
  - "managed debugging assistants (MDAs), reentrancy"
  - "illegal reentrancy"
  - "MDAs (managed debugging assistants), reentrancy"
  - "threading [.NET Framework], managed debugging assistants"
  - "managed code, debugging"
  - "native debugging, MDAs"
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# reentrancy MDA
Der `reentrancy`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird bei einem versuchten Übergang von systemeigenem Code zu verwaltetem Code aktiviert, wenn ein vorheriger Wechsel von verwaltetem Code zu systemeigenem Code nicht über einen ordnungsgemäßen Übergang erfolgt ist.  
  
## Symptome  
 Der Objektheap ist beschädigt, oder beim Übergang von systemeigenem Code zu verwaltetem Code treten andere gravierende Fehler auf.  
  
 Threads, die zwischen systemeigenem und verwaltetem Code oder umgekehrt wechseln, müssen einen ordnungsgemäßen Übergang durchführen.  Einige Erweiterungspunkte des Betriebssystems auf niedriger Ebene, z. B. der vektorielle Ausnahmehandler, erlauben jedoch Wechsel von verwaltetem zu systemeigenem Code ohne ordnungsgemäßen Übergang.  Diese Wechsel werden vom Betriebssystem, nicht von der CLR \(Common Language Runtime\) gesteuert.  Bei systemeigenem Code, der innerhalb diesen Erweiterungspunkte ausgeführt wird, darf kein Rückruf in den verwalteten Code erfolgen.  
  
## Ursache  
 Ein Erweiterungspunkt des Betriebssystems auf niedriger Ebene, z. B. der vektorielle Ausnahmehandler, wurde bei der Ausführung von verwaltetem Code aktiviert.  Der über diesen Erweiterungspunkt aufgerufene Anwendungscode versucht, einen Rückruf in den verwalteten Code durchzuführen.  
  
 Dieses Problem wird immer durch Anwendungscode verursacht.  
  
## Lösung  
 Untersuchen Sie die Stapelüberwachung für den Thread, der diesen MDA aktiviert hat.  Der Thread versucht ungültigerweise, einen Aufruf in den verwalteten Code durchzuführen.  Aus der Stapelüberwachung sollte ersichtlich sein, welcher Anwendungscode diesen Erweiterungspunkt verwendet, welcher Betriebssystemcode diesen Erweiterungspunkt bereitstellt und welcher verwaltete Code durch diesen Erweiterungspunkt unterbrochen wurde.  
  
 Der MDA wird beispielsweise bei einem Versuch aktiviert, verwalteten Code von innerhalb eines vektoriellen Ausnahmehandlers aufzurufen.  Auf dem Stapel wird der Ausnahmebehandlungscode des Betriebssystems sowie der verwaltete Code angezeigt, der eine Ausnahme wie <xref:System.DivideByZeroException> oder <xref:System.AccessViolationException> auslöst.  
  
 In diesem Beispiel ist die richtige Lösung, den vektoriellen Ausnahmehandler vollständig in nicht verwaltetem Code zu implementieren.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Der MDA meldet einen ungültigen Reentranzversuch.  Untersuchen Sie den Stapel des Threads, um zu ermitteln, warum dies geschieht und wie das Problem behoben werden kann.  Im Folgenden finden Sie eine Beispielausgabe.  
  
```  
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine <xref:System.AccessViolationException> ausgelöst.  In Versionen von Windows, die die vektorielle Ausnahmebehandlung unterstützen, wird dadurch der verwaltete vektorielle Ausnahmehandler aufgerufen.  Wenn der `reentrancy`\-MDA bereitgestellt wurde, wird der MDA beim versuchten Aufruf von `MyHandler` durch den Unterstützungscode für die vektorielle Ausnahmebehandlung des Betriebssystems aktiviert.  
  
```  
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter   
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,   
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,   
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)   
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()   
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try   
        {  
            // Dispatch on null should AV.  
            Reenter r = null;   
            r.Run();  
        }   
        catch { }  
    }  
}  
```  
  
## Siehe auch  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)