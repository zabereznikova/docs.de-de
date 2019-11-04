---
title: Auflösen von Assemblyladevorgängen
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 6a49c070bd7d2e3819044c6bb653671a2fc8199f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106996"
---
# <a name="resolve-assembly-loads"></a>Auflösen von Assemblyladevorgängen
.NET stellt das Ereignis <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> für Anwendungen bereit, die mehr Kontrolle beim Laden von Assemblys benötigen. Durch das Behandeln dieses Ereignisses kann Ihre Anwendung eine Assembly außerhalb der Prüfpfade in einen Kontext laden, vor dem Laden zwischen verschiedenen Assemblyversionen wählen, eine dynamische Assembly ausgeben und diese zurückgeben und so weiter. In diesem Thema erhalten Sie eine Anleitung zum Behandeln des Ereignisses <xref:System.AppDomain.AssemblyResolve>.  
  
> [!NOTE]
> Zum Auflösen vom Laden einer Assembly in einem reflektionsbezogenen Kontext können Sie stattdessen das Ereignis <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> verwenden.  
  
## <a name="how-the-assemblyresolve-event-works"></a>Auslösung des Ereignisses „AssemblyResolve“  
 Wenn Sie einen Handler für das Ereignis <xref:System.AppDomain.AssemblyResolve> registrieren, wird der Handler immer dann aufgerufen, wenn die Runtime eine Assembly nicht anhand deren Namen binden kann. Wenn Sie z.B. die folgende Methode aus Benutzercode aufrufen, kann das Ereignis <xref:System.AppDomain.AssemblyResolve> ausgelöst werden:  
  
- Die Methodenüberladung <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, deren erstes Argument eine Zeichenfolge ist, die den Anzeigenamen der zu ladenden Assembly darstellt (d.h. die von der Eigenschaft <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> zurückgegebene Zeichenfolge).  
  
- Die Methodenüberladung <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, deren erstes Argument ein <xref:System.Reflection.AssemblyName>-Objekt ist, das die zu ladende Assembly angibt.  
  
- Die Methodenüberladung <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
- Die Methodenüberladung <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>, das ein Objekt in einer anderen Anwendungsdomäne instantiiert.  
  
### <a name="what-the-event-handler-does"></a>Welche Aktionen der Ereignishandler ausführt  
 Der Handler für das Ereignis <xref:System.AppDomain.AssemblyResolve> erhält den Anzeigenamen der zu ladenden Assembly in der Eigenschaft <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>. Wenn der Handler den Assemblynamen nicht erkennt, gibt er `null` (C#), `Nothing` (Visual Basic) oder `nullptr` (Visual C++) zurück.  
  
 Wenn der Handler den Assemblynamen erkennt, kann er eine Assembly laden und zurückgeben, die der Anforderung entspricht. In der folgenden Liste werden einige Beispielszenarios beschrieben.  
  
- Wenn der Handler den Speicherort einer Version der Assembly kennt, kann er die Assembly mit den Methoden <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> laden und bei Erfolg die geladene Assembly zurückgeben.  
  
- Wenn der Handler auf die Datenbank von Assemblys zugreifen kann, die als Bytearrays gespeichert sind, kann er das Bytearray mit den Methodenüberladungen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> laden, die Bytearrays akzeptieren.  
  
- Der Handler kann eine dynamische Assembly generieren und diese zurückgeben.  
  
> [!NOTE]
> Der Handler muss die Assembly entweder in den load-from-Kontext, den load-Kontext oder ohne Kontext laden. Wenn der Handler die Assembly mit den Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> in den reflektionsbezogenen Kontext lädt, schlägt der Ladeversuch, der das Ereignis <xref:System.AppDomain.AssemblyResolve> ausgelöst hat, fehl.  
  
 Der Ereignishandler ist dafür verantwortlich, eine passende Assembly zurückzugeben. Der Handler kann den Anzeigename der angeforderten Assembly analysieren, indem er den Wert der <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>-Eigenschaft an den <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>-Konstruktor übergibt. Ab .NET Framework 4 kann der Handler die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um zu bestimmen, ob die aktuelle Anforderung eine Abhängigkeit von einer anderen Assembly darstellt. Diese Information kann dabei helfen, eine Assembly zu identifizieren die die Abhängigkeit erfüllt.  
  
 Der Ereignishandler kann eine Version der Assembly zurückgeben, die sich von der angeforderten Version unterscheidet.  
  
 In den meisten Fällen befindet sich die vom Handler zurückgegebene Assembly in einem load-Kontext, unabhängig vom Kontext, in der der Handler sie lädt. Wenn der Handler z.B. die <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode verwendet, um eine Assembly in einen load-from-Kontext zu laden, befindet sich die Assembly im load-Kontext, wenn der Handler sie zurückgibt. Im folgenden Kontext befindet sich die Assembly jedoch in keinem Kontext, wenn sie vom Handler zurückgegeben wird:  
  
- Der Handler lädt eine Assembly ohne Kontext.  
  
- Die <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft ist nicht NULL.  
  
- Die angeforderte Assembly, also die Assembly, die von der <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird, wurde ohne Kontext geladen.  
  
 Weitere Informationen zu Kontexten finden Sie in der Methodenüberladung <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.  
  
 Mehrere Versionen derselben Assembly können in die gleiche Anwendungsdomäne geladen werden. Diese Vorgehensweise wird jedoch nicht empfohlen, da sie zu Problemen bei der Typzuweisung führen kann. Weitere Informationen finden Sie unter [Best Practices für das Laden von Assemblys](../../framework/deployment/best-practices-for-assembly-loading.md).  
  
### <a name="what-the-event-handler-should-not-do"></a>Welche Aktionen der Ereignishandler nicht ausführen sollte  
Die erste Regeln beim Behandeln des Ereignis <xref:System.AppDomain.AssemblyResolve> ist, dass Sie nie versuchen sollten, eine Assembly zurückzugeben, die Sie nicht erkennen. Wenn Sie den Handler schreiben, sollten Sie wissen, welche Assemblys das Ereignis auslösen können. Ihr Handler sollte für andere Assemblys NULL zurückgeben.  

> [!IMPORTANT]
> Ab .NET Framework 4 wird das Ereignis <xref:System.AppDomain.AssemblyResolve> für Satellitenassemblys ausgelöst. Diese Änderung betrifft Ereignishandler, die für eine frühere Version von .NET Framework geschrieben wurden, wenn diese versuchen, alle Ladeanforderungen von Assemblys aufzulösen. Ereignishandler, die nicht erkannte Assemblys ignorieren, sind von dieser Änderung nicht betroffen: Sie geben NULL zurück. Danach wird auf die üblichen Fallbackmechanismen zurückgegriffen.  

Beim Laden einer Assembly darf der Ereignishandler nicht die Methodenüberladungen <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> verwendet, die dazu führen können, dass das Ereignis <xref:System.AppDomain.AssemblyResolve> rekursiv ausgelöst wird, da dies zu einem Stapelüberlauf führen kann. (Weitere Informationen finden Sie in der weiter oben in diesem Thema angegebenen Liste.) Dies geschieht auch, wenn Sie eine Ausnahmebehandlung für die Ladeanforderung bereitstellen, da keine Ausnahme ausgelöst wird, bis alle Ereignishandler etwas zurückgegeben haben. Deshalb führt der folgende Code zu einem Stapelüberlauf, wenn `MyAssembly` nicht gefunden werden kann:  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e) 
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    } 
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        } 
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e) 
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
} 

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System
Imports System.Reflection

Class BadExample

    Shared Sub Main()
    
        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a>Siehe auch

- [Best Practices für das Laden von Assemblys](../../framework/deployment/best-practices-for-assembly-loading.md)
- [Verwenden von Anwendungsdomänen](../../framework/app-domains/use.md)
