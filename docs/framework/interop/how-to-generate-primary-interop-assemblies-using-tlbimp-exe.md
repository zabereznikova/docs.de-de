---
title: 'Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“'
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: e46295b89b042452cb6e303302a8b88d68d58426
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123908"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a>Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“

Es gibt zwei Möglichkeiten, eine primäre Interop-Assembly zu generieren:

- Verwenden von [„Tlbimp.exe“ (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md), das im Windows SDK bereitgestellt wird.

  Die einfachste Möglichkeit zum Erstellen primärer Interop-Assemblys besteht darin, [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md) zu verwenden. "Tlbimp.exe" bietet die folgenden Schutzvorrichtungen:

  - Es prüft auf andere registrierte primäre Interop-Assemblys, bevor es neue Interop-Assemblys für irgendwelche geschachtelten Typbibliotheksverweise erstellt.

  - Es kann die primäre Interop-Assembly nicht ausgeben, wenn Sie nicht entweder den Container oder den Dateinamen angeben, um der primären Interop-Assembly einen starken Namen zu geben.

  - Es kann keine primäre Interop-Assembly ausgeben, wenn Sie keine Verweise auf abhängige Assemblys angeben.

  - Es kann keine primäre Interop-Assembly ausgeben, wenn Sie Verweise auf abhängige Assemblys hinzufügen, die keine primären Interop-Assemblys sind.

- Manuelles Erstellen von primären Interop-Assemblys in Quellcode, indem eine Sprache verwendet wird, die mit der Common Language Specification (CLS) kompatibel ist, beispielsweise C#. Dieser Ansatz ist hilfreich, wenn keine Typbibliothek verfügbar ist.

Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren. Ausführliche Informationen finden Sie unter [Erstellen eines Schlüsselpaares](../../standard/assembly/create-public-private-key-pair.md).

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a>So generieren Sie eine primäre Interop-Assemblys mit "Tlbimp.exe"

1. Geben Sie an der Eingabeaufforderung Folgendes ein:

    **tlbimp** *tlbfile*  **/primary /keyfile:** *Dateiname* **/out:** *Assemblyname*

    In diesem Befehl ist *tlbfile* die Datei, die die COM-Typbibliothek enthält, *filename* der Name des Containers oder der Datei, die das Schlüsselpaar enthalten, und *assemblyname* der Name der zu unterzeichnenden Assembly mit einem starken Namen.

Primäre Interop-Assemblys können nur auf andere primäre Interop-Assemblys verweisen. Wenn Ihre Assembly auf Typen aus einer COM-Typbibliothek eines Drittanbieters verweist, müssen Sie eine primäre Interop-Assembly von dem Herausgeber abrufen, bevor Sie Ihre primäre Interop-Assembly generieren können. Wenn Sie der Herausgeber sind, müssen Sie eine primäre Interop-Assembly für die abhängige Typbibliothek generieren, bevor Sie die verweisende primäre Interop-Assembly generieren.

Eine abhängige primäre Interop-Assembly mit einer Versionsnummer, die von der der ursprünglichen Typbibliothek abweicht, kann nicht erkennt werden, wenn sie im aktuellen Verzeichnis installiert ist. Sie müssen die abhängige primäre Interop-Assembly in der Windows-Registrierung registrieren oder die **/reference**-Option verwenden, um sicherzustellen, dass „Tlbimp.exe“ die abhängige DLL finden kann.

Sie können auch mehrere Versionen einer Typbibliothek einschließen. Anweisungen hierzu finden Sie unter [Vorgehensweise: Einschließen mehrerer Versionen von Typbibliotheken](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die COM-Typbibliothek `LibUtil.tlb` importiert und die Assembly `LibUtil.dll` mit einem starken Namen signiert, indem die Schlüsseldatei `CompanyA.snk` verwendet wird. Dadurch, dass kein spezieller Namespacename angegeben ist, wird in diesem Beispiel wird der Standardnamespace, `LibUtil`, erstellt.

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

Für einen aussagekräftigeren Namen (mit der Benennungsrichtline *Herstellername*.*Bibliotheksname*) überschreibt das folgende Beispiel den Standardnamen für die Assemblydatei und den Namespace.

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

Im folgenden Beispiel wird `MyLib.tlb` importiert, in der auf `CompanyA.LibUtil.dll` verwiesen wird, und wird die Assembly `CompanyB.MyLib.dll` über die Schlüsseldatei `CompanyB.snk` mit einem starken Namen signiert. Der Namespacename `CompanyB.MyLib` wird verwendet, um den Standardnamespacenamen zu überschreiben.

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a>Siehe auch

- [How to: Registrieren primärer Interopassemblys](how-to-register-primary-interop-assemblies.md)
