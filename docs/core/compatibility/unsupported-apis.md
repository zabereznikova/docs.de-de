---
title: Nicht unterstützte APIs in .NET Core und .NET 5 (und höher)
titleSuffix: ''
description: Hier erfahren Sie, welche .NET-APIs in .NET Core und .NET 5.0 und höheren Versionen immer eine Ausnahme auslösen.
ms.date: 10/13/2020
ms.openlocfilehash: 1bd41192d0d6752d2b659da9fb6387dac321b2c3
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593265"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="9cab2-103">APIs, die in .NET Core und .NET 5 und höher immer Ausnahmen auslösen</span><span class="sxs-lookup"><span data-stu-id="9cab2-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="9cab2-104">Die folgenden APIs lösen in .NET 5.0 und höheren Versionen (einschließlich aller .NET Core-Versionen) auf allen oder einer Teilmenge aller Plattformen immer eine <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="9cab2-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="9cab2-105">In diesem Artikel werden die betroffenen APIs nach Namespace organisiert.</span><span class="sxs-lookup"><span data-stu-id="9cab2-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9cab2-106">Dies ist nicht die endgültige Fassung dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="9cab2-106">This article is a work-in-progress.</span></span> <span data-ttu-id="9cab2-107">Er enthält keine vollständige Liste der APIs, die Ausnahmen in .NET 5 und höher auslösen.</span><span class="sxs-lookup"><span data-stu-id="9cab2-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="9cab2-108">In diesem Artikel sind die expliziten Schnittstellenimplementierungen für die binäre Serialisierung, die in .NET 5 und höher eine Ausnahme auslösen, nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9cab2-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="9cab2-109">Weitere Informationen finden Sie unter [Binäre Serialisierung](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="9cab2-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="9cab2-110">System</span><span class="sxs-lookup"><span data-stu-id="9cab2-110">System</span></span>

| <span data-ttu-id="9cab2-111">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-111">Member</span></span> | <span data-ttu-id="9cab2-112">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-113">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-114">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="9cab2-115">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="9cab2-116">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-117">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="9cab2-118">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9cab2-119">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="9cab2-120">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-121">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-122">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="9cab2-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="9cab2-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="9cab2-124">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-124">Member</span></span> | <span data-ttu-id="9cab2-125">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-126">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-127">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-128">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="9cab2-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="9cab2-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="9cab2-130">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-130">Member</span></span> | <span data-ttu-id="9cab2-131">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-132">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-133">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-134">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="9cab2-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="9cab2-135">System.Configuration</span></span>

| <span data-ttu-id="9cab2-136">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-136">Member</span></span> | <span data-ttu-id="9cab2-137">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9cab2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="9cab2-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="9cab2-139">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="9cab2-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="9cab2-140">System.Console</span></span>

| <span data-ttu-id="9cab2-141">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-141">Member</span></span> | <span data-ttu-id="9cab2-142">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="9cab2-143">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-143">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-145">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-145">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-147">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-147">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-149">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-149">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9cab2-151">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-152">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-153">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-154">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-154">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-155"><xref:System.Console.Title?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9cab2-156">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-156">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-158">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-158">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-160">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-160">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-162">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-162">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-164">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="9cab2-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="9cab2-165">System.Data.Common</span></span>

| <span data-ttu-id="9cab2-166">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-166">Member</span></span> | <span data-ttu-id="9cab2-167">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9cab2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (löst <xref:System.NotSupportedException> aus)</span><span class="sxs-lookup"><span data-stu-id="9cab2-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="9cab2-169">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="9cab2-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="9cab2-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="9cab2-171">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-171">Member</span></span> | <span data-ttu-id="9cab2-172">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="9cab2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-174">Linux</span><span class="sxs-lookup"><span data-stu-id="9cab2-174">Linux</span></span> |
| <span data-ttu-id="9cab2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-176">Linux</span><span class="sxs-lookup"><span data-stu-id="9cab2-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="9cab2-177">macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="9cab2-178">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-179">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-180">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="9cab2-181">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="9cab2-182">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="9cab2-183">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-183">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="9cab2-184">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-184">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-186">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-186">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="9cab2-188">macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-188">macOS</span></span> |
| <span data-ttu-id="9cab2-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-190">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-190">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="9cab2-191">System.IO</span><span class="sxs-lookup"><span data-stu-id="9cab2-191">System.IO</span></span>

| <span data-ttu-id="9cab2-192">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-192">Member</span></span> | <span data-ttu-id="9cab2-193">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-193">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-194">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-194">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-195">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-195">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="9cab2-196">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="9cab2-196">System.IO.Pipes</span></span>

| <span data-ttu-id="9cab2-197">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-197">Member</span></span> | <span data-ttu-id="9cab2-198">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-198">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="9cab2-199">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="9cab2-200">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9cab2-201">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-201">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="9cab2-202">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-202">Linux and macOS</span></span> |
| <span data-ttu-id="9cab2-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-204">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-204">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="9cab2-205">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-205">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="9cab2-206">System. Media</span><span class="sxs-lookup"><span data-stu-id="9cab2-206">System.Media</span></span>

| <span data-ttu-id="9cab2-207">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-207">Member</span></span> | <span data-ttu-id="9cab2-208">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-208">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-209">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-209">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="9cab2-210">System.Net</span><span class="sxs-lookup"><span data-stu-id="9cab2-210">System.Net</span></span>

| <span data-ttu-id="9cab2-211">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-211">Member</span></span> | <span data-ttu-id="9cab2-212">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-212">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-213">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-213">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-214">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-214">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-215">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-215">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-216">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-216">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-217">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-217">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-218">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-219">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-219">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-220">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-221">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-221">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-222">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-222">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-223">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-223">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="9cab2-224">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-224">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-225">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-225">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-226">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-226">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-227">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-227">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-228">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-228">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-229">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-229">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="9cab2-230">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="9cab2-230">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="9cab2-231">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-231">Member</span></span> | <span data-ttu-id="9cab2-232">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-232">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-233">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="9cab2-233">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="9cab2-234">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="9cab2-234">System.Net.Sockets</span></span>

| <span data-ttu-id="9cab2-235">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-235">Member</span></span> | <span data-ttu-id="9cab2-236">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-236">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="9cab2-237">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-237">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-238">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-238">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="9cab2-239">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="9cab2-239">System.Net.WebSockets</span></span>

| <span data-ttu-id="9cab2-240">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-240">Member</span></span> | <span data-ttu-id="9cab2-241">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-241">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="9cab2-242">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-242">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="9cab2-243">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="9cab2-243">System.Reflection</span></span>

| <span data-ttu-id="9cab2-244">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-244">Member</span></span> | <span data-ttu-id="9cab2-245">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-245">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-246">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-246">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-247">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-248">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-248">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-249">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="9cab2-250">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-251">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-251">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="9cab2-252">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-252">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="9cab2-253">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="9cab2-253">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="9cab2-254">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-254">Member</span></span> | <span data-ttu-id="9cab2-255">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-255">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="9cab2-256">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-256">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="9cab2-257">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="9cab2-257">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="9cab2-258">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-258">Member</span></span> | <span data-ttu-id="9cab2-259">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-259">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-260">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="9cab2-261">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-262">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-262">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-263">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-263">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-264">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-265">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-265">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-266">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-266">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="9cab2-267">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="9cab2-267">System.Runtime.Serialization</span></span>

| <span data-ttu-id="9cab2-268">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-268">Member</span></span> | <span data-ttu-id="9cab2-269">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-269">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="9cab2-270">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-270">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="9cab2-271">System.Security</span><span class="sxs-lookup"><span data-stu-id="9cab2-271">System.Security</span></span>

| <span data-ttu-id="9cab2-272">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-272">Member</span></span> | <span data-ttu-id="9cab2-273">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-273">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="9cab2-274">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-274">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9cab2-275">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-275">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-276">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-276">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="9cab2-277">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-277">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="9cab2-278">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-278">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="9cab2-279">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-279">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="9cab2-280">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-280">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="9cab2-281">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9cab2-282">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-282">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="9cab2-283">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-283">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="9cab2-284">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-284">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-285">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="9cab2-286">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-286">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="9cab2-287">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-287">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="9cab2-288">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="9cab2-288">System.Security.Claims</span></span>

| <span data-ttu-id="9cab2-289">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-289">Member</span></span> | <span data-ttu-id="9cab2-290">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-290">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-291">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-292">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="9cab2-293">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-294">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-294">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-295">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-295">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="9cab2-296">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="9cab2-296">System.Security.Cryptography</span></span>

| <span data-ttu-id="9cab2-297">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-297">Member</span></span> | <span data-ttu-id="9cab2-298">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-298">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-299">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-299">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="9cab2-300">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="9cab2-301">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="9cab2-302">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="9cab2-303">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9cab2-304">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="9cab2-305">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="9cab2-306">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="9cab2-307">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="9cab2-308">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="9cab2-309">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="9cab2-310">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="9cab2-311">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="9cab2-312">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-312">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9cab2-313">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="9cab2-314">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-315">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-316">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-317">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-317">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-318">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9cab2-319">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-319">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-320">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-320">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-321">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-322">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="9cab2-322">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-323">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-323">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-324">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="9cab2-325">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-325">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-326">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-326">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="9cab2-327">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="9cab2-327">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="9cab2-328">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-328">Member</span></span> | <span data-ttu-id="9cab2-329">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-329">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="9cab2-330">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="9cab2-331">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="9cab2-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="9cab2-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="9cab2-333">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-333">Member</span></span> | <span data-ttu-id="9cab2-334">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-335">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-336">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-337">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-337">All</span></span> |
| <span data-ttu-id="9cab2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="9cab2-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="9cab2-339">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="9cab2-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="9cab2-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="9cab2-341">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-341">Member</span></span> | <span data-ttu-id="9cab2-342">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-343">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="9cab2-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="9cab2-344">System.Security.Policy</span></span>

| <span data-ttu-id="9cab2-345">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-345">Member</span></span> | <span data-ttu-id="9cab2-346">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-347">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="9cab2-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="9cab2-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="9cab2-349">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-349">Member</span></span> | <span data-ttu-id="9cab2-350">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="9cab2-351">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="9cab2-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="9cab2-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="9cab2-353">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-353">Member</span></span> | <span data-ttu-id="9cab2-354">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-355">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="9cab2-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="9cab2-356">System.Threading</span></span>

| <span data-ttu-id="9cab2-357">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-357">Member</span></span> | <span data-ttu-id="9cab2-358">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-359">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-360">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="9cab2-361">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="9cab2-362">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="9cab2-363">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="9cab2-364">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="9cab2-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="9cab2-365">System.Xml</span></span>

| <span data-ttu-id="9cab2-366">Member</span><span class="sxs-lookup"><span data-stu-id="9cab2-366">Member</span></span> | <span data-ttu-id="9cab2-367">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="9cab2-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-368">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-369">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="9cab2-370">Alle</span><span class="sxs-lookup"><span data-stu-id="9cab2-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="9cab2-371">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cab2-371">See also</span></span>

- [<span data-ttu-id="9cab2-372">Breaking Changes für die Migration von .NET Framework zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="9cab2-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="9cab2-373">Binäre Serialisierung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="9cab2-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="9cab2-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="9cab2-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
