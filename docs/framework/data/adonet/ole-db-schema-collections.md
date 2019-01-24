---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f753f35aab0a0200da5de463a73abb9813253d11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658454"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="7981a-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7981a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="7981a-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="7981a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="7981a-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7981a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="7981a-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7981a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7981a-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-106">Tables</span></span>  
  
-   <span data-ttu-id="7981a-107">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-107">Columns</span></span>  
  
-   <span data-ttu-id="7981a-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-108">Procedures</span></span>  
  
-   <span data-ttu-id="7981a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7981a-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7981a-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="7981a-110">Catalog</span></span>  
  
-   <span data-ttu-id="7981a-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7981a-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-112">Tables</span></span>  
  
|<span data-ttu-id="7981a-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-113">ColumnName</span></span>|<span data-ttu-id="7981a-114">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-116">String</span></span>|  
|<span data-ttu-id="7981a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-118">String</span></span>|  
|<span data-ttu-id="7981a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-119">TABLE_NAME</span></span>|<span data-ttu-id="7981a-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-120">String</span></span>|  
|<span data-ttu-id="7981a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-121">TABLE_TYPE</span></span>|<span data-ttu-id="7981a-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-122">String</span></span>|  
|<span data-ttu-id="7981a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-123">TABLE_GUID</span></span>|<span data-ttu-id="7981a-124">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-124">Guid</span></span>|  
|<span data-ttu-id="7981a-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-125">DESCRIPTION</span></span>|<span data-ttu-id="7981a-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-126">String</span></span>|  
|<span data-ttu-id="7981a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-127">TABLE_PROPID</span></span>|<span data-ttu-id="7981a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-128">Int64</span></span>|  
|<span data-ttu-id="7981a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-129">DATE_CREATED</span></span>|<span data-ttu-id="7981a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-130">DateTime</span></span>|  
|<span data-ttu-id="7981a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7981a-133">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-133">Columns</span></span>  
  
|<span data-ttu-id="7981a-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-134">ColumnName</span></span>|<span data-ttu-id="7981a-135">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-137">String</span></span>|  
|<span data-ttu-id="7981a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-139">String</span></span>|  
|<span data-ttu-id="7981a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-140">TABLE_NAME</span></span>|<span data-ttu-id="7981a-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-141">String</span></span>|  
|<span data-ttu-id="7981a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-142">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-143">String</span></span>|  
|<span data-ttu-id="7981a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-144">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-145">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-145">Guid</span></span>|  
|<span data-ttu-id="7981a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-147">Int64</span></span>|  
|<span data-ttu-id="7981a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-149">Int64</span></span>|  
|<span data-ttu-id="7981a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7981a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-151">Boolean</span></span>|  
|<span data-ttu-id="7981a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7981a-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-153">String</span></span>|  
|<span data-ttu-id="7981a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7981a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="7981a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-155">Int64</span></span>|  
|<span data-ttu-id="7981a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-156">IS_NULLABLE</span></span>|<span data-ttu-id="7981a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-157">Boolean</span></span>|  
|<span data-ttu-id="7981a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-158">DATA_TYPE</span></span>|<span data-ttu-id="7981a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-159">Int32</span></span>|  
|<span data-ttu-id="7981a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-160">TYPE_GUID</span></span>|<span data-ttu-id="7981a-161">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-161">Guid</span></span>|  
|<span data-ttu-id="7981a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7981a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-163">Int64</span></span>|  
|<span data-ttu-id="7981a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7981a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-165">Int64</span></span>|  
|<span data-ttu-id="7981a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7981a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-167">Int32</span></span>|  
|<span data-ttu-id="7981a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7981a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="7981a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-169">Int16</span></span>|  
|<span data-ttu-id="7981a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="7981a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-171">Int64</span></span>|  
|<span data-ttu-id="7981a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7981a-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-173">String</span></span>|  
|<span data-ttu-id="7981a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7981a-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-175">String</span></span>|  
|<span data-ttu-id="7981a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7981a-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-177">String</span></span>|  
|<span data-ttu-id="7981a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="7981a-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-179">String</span></span>|  
|<span data-ttu-id="7981a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7981a-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-181">String</span></span>|  
|<span data-ttu-id="7981a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-182">COLLATION_NAME</span></span>|<span data-ttu-id="7981a-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-183">String</span></span>|  
|<span data-ttu-id="7981a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7981a-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-185">String</span></span>|  
|<span data-ttu-id="7981a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7981a-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-187">String</span></span>|  
|<span data-ttu-id="7981a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="7981a-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-189">String</span></span>|  
|<span data-ttu-id="7981a-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-190">DESCRIPTION</span></span>|<span data-ttu-id="7981a-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-191">String</span></span>|  
|<span data-ttu-id="7981a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="7981a-192">COLUMN_LCID</span></span>|<span data-ttu-id="7981a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-193">Int32</span></span>|  
|<span data-ttu-id="7981a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="7981a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="7981a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-195">Int32</span></span>|  
|<span data-ttu-id="7981a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="7981a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="7981a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-197">Int32</span></span>|  
|<span data-ttu-id="7981a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="7981a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="7981a-199">Byte[]</span></span>|  
|<span data-ttu-id="7981a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="7981a-200">IS_COMPUTED</span></span>|<span data-ttu-id="7981a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7981a-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-202">Procedures</span></span>  
  
|<span data-ttu-id="7981a-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-203">ColumnName</span></span>|<span data-ttu-id="7981a-204">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7981a-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-206">String</span></span>|  
|<span data-ttu-id="7981a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7981a-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-208">String</span></span>|  
|<span data-ttu-id="7981a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="7981a-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-210">String</span></span>|  
|<span data-ttu-id="7981a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7981a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-212">Int16</span></span>|  
|<span data-ttu-id="7981a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7981a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7981a-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-214">String</span></span>|  
|<span data-ttu-id="7981a-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-215">DESCRIPTION</span></span>|<span data-ttu-id="7981a-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-216">String</span></span>|  
|<span data-ttu-id="7981a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-217">DATE_CREATED</span></span>|<span data-ttu-id="7981a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-218">DateTime</span></span>|  
|<span data-ttu-id="7981a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7981a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7981a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7981a-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-222">ColumnName</span></span>|<span data-ttu-id="7981a-223">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7981a-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-225">String</span></span>|  
|<span data-ttu-id="7981a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7981a-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-227">String</span></span>|  
|<span data-ttu-id="7981a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="7981a-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-229">String</span></span>|  
|<span data-ttu-id="7981a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="7981a-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-231">String</span></span>|  
|<span data-ttu-id="7981a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-233">Int32</span></span>|  
|<span data-ttu-id="7981a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="7981a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-235">Int32</span></span>|  
|<span data-ttu-id="7981a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="7981a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-237">Boolean</span></span>|  
|<span data-ttu-id="7981a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="7981a-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-239">String</span></span>|  
|<span data-ttu-id="7981a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-240">IS_NULLABLE</span></span>|<span data-ttu-id="7981a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-241">Boolean</span></span>|  
|<span data-ttu-id="7981a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-242">DATA_TYPE</span></span>|<span data-ttu-id="7981a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-243">Int32</span></span>|  
|<span data-ttu-id="7981a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7981a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-245">Int64</span></span>|  
|<span data-ttu-id="7981a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7981a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-247">Int64</span></span>|  
|<span data-ttu-id="7981a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7981a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-249">Int32</span></span>|  
|<span data-ttu-id="7981a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7981a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="7981a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-251">Int16</span></span>|  
|<span data-ttu-id="7981a-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-252">DESCRIPTION</span></span>|<span data-ttu-id="7981a-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-253">String</span></span>|  
|<span data-ttu-id="7981a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-254">TYPE_NAME</span></span>|<span data-ttu-id="7981a-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-255">String</span></span>|  
|<span data-ttu-id="7981a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="7981a-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="7981a-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="7981a-258">Catalog</span></span>  
  
|<span data-ttu-id="7981a-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-259">ColumnName</span></span>|<span data-ttu-id="7981a-260">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-261">CATALOG_NAME</span></span>|<span data-ttu-id="7981a-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-262">String</span></span>|  
|<span data-ttu-id="7981a-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-263">DESCRIPTION</span></span>|<span data-ttu-id="7981a-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7981a-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-265">Indexes</span></span>  
  
|<span data-ttu-id="7981a-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-266">ColumnName</span></span>|<span data-ttu-id="7981a-267">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-269">String</span></span>|  
|<span data-ttu-id="7981a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-271">String</span></span>|  
|<span data-ttu-id="7981a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-272">TABLE_NAME</span></span>|<span data-ttu-id="7981a-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-273">String</span></span>|  
|<span data-ttu-id="7981a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="7981a-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-275">String</span></span>|  
|<span data-ttu-id="7981a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="7981a-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-277">String</span></span>|  
|<span data-ttu-id="7981a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-278">INDEX_NAME</span></span>|<span data-ttu-id="7981a-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-279">String</span></span>|  
|<span data-ttu-id="7981a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7981a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="7981a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-281">Boolean</span></span>|  
|<span data-ttu-id="7981a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7981a-282">UNIQUE</span></span>|<span data-ttu-id="7981a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-283">Boolean</span></span>|  
|<span data-ttu-id="7981a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7981a-284">CLUSTERED</span></span>|<span data-ttu-id="7981a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-285">Boolean</span></span>|  
|<span data-ttu-id="7981a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-286">TYPE</span></span>|<span data-ttu-id="7981a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-287">Int32</span></span>|  
|<span data-ttu-id="7981a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7981a-288">FILL_FACTOR</span></span>|<span data-ttu-id="7981a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-289">Int32</span></span>|  
|<span data-ttu-id="7981a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7981a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="7981a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-291">Int32</span></span>|  
|<span data-ttu-id="7981a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="7981a-292">NULLS</span></span>|<span data-ttu-id="7981a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-293">Int32</span></span>|  
|<span data-ttu-id="7981a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7981a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7981a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-295">Boolean</span></span>|  
|<span data-ttu-id="7981a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7981a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="7981a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-297">Boolean</span></span>|  
|<span data-ttu-id="7981a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-298">NULL_COLLATION</span></span>|<span data-ttu-id="7981a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-299">Int32</span></span>|  
|<span data-ttu-id="7981a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-301">Int64</span></span>|  
|<span data-ttu-id="7981a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-302">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-303">String</span></span>|  
|<span data-ttu-id="7981a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-304">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-305">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-305">Guid</span></span>|  
|<span data-ttu-id="7981a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-307">Int64</span></span>|  
|<span data-ttu-id="7981a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-308">COLLATION</span></span>|<span data-ttu-id="7981a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-309">Int16</span></span>|  
|<span data-ttu-id="7981a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7981a-310">CARDINALITY</span></span>|<span data-ttu-id="7981a-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="7981a-311">Decimal</span></span>|  
|<span data-ttu-id="7981a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="7981a-312">PAGES</span></span>|<span data-ttu-id="7981a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-313">Int32</span></span>|  
|<span data-ttu-id="7981a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7981a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="7981a-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-315">String</span></span>|  
|<span data-ttu-id="7981a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7981a-316">INTEGRATED</span></span>|<span data-ttu-id="7981a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="7981a-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7981a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="7981a-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7981a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7981a-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-320">Tables</span></span>  
  
-   <span data-ttu-id="7981a-321">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-321">Columns</span></span>  
  
-   <span data-ttu-id="7981a-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-322">Procedures</span></span>  
  
-   <span data-ttu-id="7981a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7981a-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7981a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7981a-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7981a-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7981a-325">Views</span></span>  
  
-   <span data-ttu-id="7981a-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7981a-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-327">Tables</span></span>  
  
|<span data-ttu-id="7981a-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-328">ColumnName</span></span>|<span data-ttu-id="7981a-329">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-331">String</span></span>|  
|<span data-ttu-id="7981a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-333">String</span></span>|  
|<span data-ttu-id="7981a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-334">TABLE_NAME</span></span>|<span data-ttu-id="7981a-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-335">String</span></span>|  
|<span data-ttu-id="7981a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-336">TABLE_TYPE</span></span>|<span data-ttu-id="7981a-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-337">String</span></span>|  
|<span data-ttu-id="7981a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-338">TABLE_GUID</span></span>|<span data-ttu-id="7981a-339">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-339">Guid</span></span>|  
|<span data-ttu-id="7981a-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-340">DESCRIPTION</span></span>|<span data-ttu-id="7981a-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-341">String</span></span>|  
|<span data-ttu-id="7981a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-342">TABLE_PROPID</span></span>|<span data-ttu-id="7981a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-343">Int64</span></span>|  
|<span data-ttu-id="7981a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-344">DATE_CREATED</span></span>|<span data-ttu-id="7981a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-345">DateTime</span></span>|  
|<span data-ttu-id="7981a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7981a-348">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-348">Columns</span></span>  
  
|<span data-ttu-id="7981a-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-349">ColumnName</span></span>|<span data-ttu-id="7981a-350">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-352">String</span></span>|  
|<span data-ttu-id="7981a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-354">String</span></span>|  
|<span data-ttu-id="7981a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-355">TABLE_NAME</span></span>|<span data-ttu-id="7981a-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-356">String</span></span>|  
|<span data-ttu-id="7981a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-357">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-358">String</span></span>|  
|<span data-ttu-id="7981a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-359">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-360">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-360">Guid</span></span>|  
|<span data-ttu-id="7981a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-362">Int64</span></span>|  
|<span data-ttu-id="7981a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-364">Int64</span></span>|  
|<span data-ttu-id="7981a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7981a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-366">Boolean</span></span>|  
|<span data-ttu-id="7981a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7981a-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-368">String</span></span>|  
|<span data-ttu-id="7981a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7981a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="7981a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-370">Int64</span></span>|  
|<span data-ttu-id="7981a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-371">IS_NULLABLE</span></span>|<span data-ttu-id="7981a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-372">Boolean</span></span>|  
|<span data-ttu-id="7981a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-373">DATA_TYPE</span></span>|<span data-ttu-id="7981a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-374">Int32</span></span>|  
|<span data-ttu-id="7981a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-375">TYPE_GUID</span></span>|<span data-ttu-id="7981a-376">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-376">Guid</span></span>|  
|<span data-ttu-id="7981a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7981a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-378">Int64</span></span>|  
|<span data-ttu-id="7981a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7981a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-380">Int64</span></span>|  
|<span data-ttu-id="7981a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7981a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-382">Int32</span></span>|  
|<span data-ttu-id="7981a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7981a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="7981a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-384">Int16</span></span>|  
|<span data-ttu-id="7981a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="7981a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-386">Int64</span></span>|  
|<span data-ttu-id="7981a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7981a-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-388">String</span></span>|  
|<span data-ttu-id="7981a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7981a-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-390">String</span></span>|  
|<span data-ttu-id="7981a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7981a-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-392">String</span></span>|  
|<span data-ttu-id="7981a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="7981a-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-394">String</span></span>|  
|<span data-ttu-id="7981a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7981a-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-396">String</span></span>|  
|<span data-ttu-id="7981a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-397">COLLATION_NAME</span></span>|<span data-ttu-id="7981a-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-398">String</span></span>|  
|<span data-ttu-id="7981a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7981a-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-400">String</span></span>|  
|<span data-ttu-id="7981a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7981a-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-402">String</span></span>|  
|<span data-ttu-id="7981a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="7981a-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-404">String</span></span>|  
|<span data-ttu-id="7981a-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-405">DESCRIPTION</span></span>|<span data-ttu-id="7981a-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7981a-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-407">Procedures</span></span>  
  
|<span data-ttu-id="7981a-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-408">ColumnName</span></span>|<span data-ttu-id="7981a-409">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7981a-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-411">String</span></span>|  
|<span data-ttu-id="7981a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7981a-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-413">String</span></span>|  
|<span data-ttu-id="7981a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="7981a-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-415">String</span></span>|  
|<span data-ttu-id="7981a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7981a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-417">Int16</span></span>|  
|<span data-ttu-id="7981a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7981a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7981a-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-419">String</span></span>|  
|<span data-ttu-id="7981a-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-420">DESCRIPTION</span></span>|<span data-ttu-id="7981a-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-421">String</span></span>|  
|<span data-ttu-id="7981a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-422">DATE_CREATED</span></span>|<span data-ttu-id="7981a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-423">DateTime</span></span>|  
|<span data-ttu-id="7981a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7981a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7981a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7981a-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-427">ColumnName</span></span>|<span data-ttu-id="7981a-428">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7981a-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-430">String</span></span>|  
|<span data-ttu-id="7981a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7981a-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-432">String</span></span>|  
|<span data-ttu-id="7981a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="7981a-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-434">String</span></span>|  
|<span data-ttu-id="7981a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-435">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-436">String</span></span>|  
|<span data-ttu-id="7981a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-437">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-438">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-438">Guid</span></span>|  
|<span data-ttu-id="7981a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-440">Int64</span></span>|  
|<span data-ttu-id="7981a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="7981a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="7981a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-442">Int64</span></span>|  
|<span data-ttu-id="7981a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-444">Int64</span></span>|  
|<span data-ttu-id="7981a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-445">IS_NULLABLE</span></span>|<span data-ttu-id="7981a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-446">Boolean</span></span>|  
|<span data-ttu-id="7981a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-447">DATA_TYPE</span></span>|<span data-ttu-id="7981a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-448">Int32</span></span>|  
|<span data-ttu-id="7981a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-449">TYPE_GUID</span></span>|<span data-ttu-id="7981a-450">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-450">Guid</span></span>|  
|<span data-ttu-id="7981a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7981a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-452">Int64</span></span>|  
|<span data-ttu-id="7981a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7981a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-454">Int64</span></span>|  
|<span data-ttu-id="7981a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7981a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-456">Int32</span></span>|  
|<span data-ttu-id="7981a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7981a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="7981a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-458">Int16</span></span>|  
|<span data-ttu-id="7981a-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-459">DESCRIPTION</span></span>|<span data-ttu-id="7981a-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-460">String</span></span>|  
|<span data-ttu-id="7981a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7981a-461">OVERLOAD</span></span>|<span data-ttu-id="7981a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7981a-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7981a-463">Views</span></span>  
  
|<span data-ttu-id="7981a-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-464">ColumnName</span></span>|<span data-ttu-id="7981a-465">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-467">String</span></span>|  
|<span data-ttu-id="7981a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-469">String</span></span>|  
|<span data-ttu-id="7981a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-470">TABLE_NAME</span></span>|<span data-ttu-id="7981a-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-471">String</span></span>|  
|<span data-ttu-id="7981a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7981a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="7981a-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-473">String</span></span>|  
|<span data-ttu-id="7981a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-474">CHECK_OPTION</span></span>|<span data-ttu-id="7981a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-475">Boolean</span></span>|  
|<span data-ttu-id="7981a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="7981a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-477">Boolean</span></span>|  
|<span data-ttu-id="7981a-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-478">DESCRIPTION</span></span>|<span data-ttu-id="7981a-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-479">String</span></span>|  
|<span data-ttu-id="7981a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-480">DATE_CREATED</span></span>|<span data-ttu-id="7981a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-481">DateTime</span></span>|  
|<span data-ttu-id="7981a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7981a-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-484">Indexes</span></span>  
  
|<span data-ttu-id="7981a-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-485">ColumnName</span></span>|<span data-ttu-id="7981a-486">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-488">String</span></span>|  
|<span data-ttu-id="7981a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-490">String</span></span>|  
|<span data-ttu-id="7981a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-491">TABLE_NAME</span></span>|<span data-ttu-id="7981a-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-492">String</span></span>|  
|<span data-ttu-id="7981a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="7981a-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-494">String</span></span>|  
|<span data-ttu-id="7981a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="7981a-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-496">String</span></span>|  
|<span data-ttu-id="7981a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-497">INDEX_NAME</span></span>|<span data-ttu-id="7981a-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-498">String</span></span>|  
|<span data-ttu-id="7981a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7981a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="7981a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-500">Boolean</span></span>|  
|<span data-ttu-id="7981a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7981a-501">UNIQUE</span></span>|<span data-ttu-id="7981a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-502">Boolean</span></span>|  
|<span data-ttu-id="7981a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7981a-503">CLUSTERED</span></span>|<span data-ttu-id="7981a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-504">Boolean</span></span>|  
|<span data-ttu-id="7981a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-505">TYPE</span></span>|<span data-ttu-id="7981a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-506">Int32</span></span>|  
|<span data-ttu-id="7981a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7981a-507">FILL_FACTOR</span></span>|<span data-ttu-id="7981a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-508">Int32</span></span>|  
|<span data-ttu-id="7981a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7981a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="7981a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-510">Int32</span></span>|  
|<span data-ttu-id="7981a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="7981a-511">NULLS</span></span>|<span data-ttu-id="7981a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-512">Int32</span></span>|  
|<span data-ttu-id="7981a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7981a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7981a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-514">Boolean</span></span>|  
|<span data-ttu-id="7981a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7981a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="7981a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-516">Boolean</span></span>|  
|<span data-ttu-id="7981a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-517">NULL_COLLATION</span></span>|<span data-ttu-id="7981a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-518">Int32</span></span>|  
|<span data-ttu-id="7981a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-520">Int64</span></span>|  
|<span data-ttu-id="7981a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-521">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-522">String</span></span>|  
|<span data-ttu-id="7981a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-523">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-524">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-524">Guid</span></span>|  
|<span data-ttu-id="7981a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-526">Int64</span></span>|  
|<span data-ttu-id="7981a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-527">COLLATION</span></span>|<span data-ttu-id="7981a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-528">Int16</span></span>|  
|<span data-ttu-id="7981a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7981a-529">CARDINALITY</span></span>|<span data-ttu-id="7981a-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="7981a-530">Decimal</span></span>|  
|<span data-ttu-id="7981a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="7981a-531">PAGES</span></span>|<span data-ttu-id="7981a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-532">Int32</span></span>|  
|<span data-ttu-id="7981a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7981a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="7981a-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-534">String</span></span>|  
|<span data-ttu-id="7981a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7981a-535">INTEGRATED</span></span>|<span data-ttu-id="7981a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="7981a-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7981a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="7981a-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7981a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7981a-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-539">Tables</span></span>  
  
-   <span data-ttu-id="7981a-540">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-540">Columns</span></span>  
  
-   <span data-ttu-id="7981a-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-541">Procedures</span></span>  
  
-   <span data-ttu-id="7981a-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7981a-542">Views</span></span>  
  
-   <span data-ttu-id="7981a-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7981a-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7981a-544">Tables</span></span>  
  
|<span data-ttu-id="7981a-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-545">ColumnName</span></span>|<span data-ttu-id="7981a-546">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-548">String</span></span>|  
|<span data-ttu-id="7981a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-550">String</span></span>|  
|<span data-ttu-id="7981a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-551">TABLE_NAME</span></span>|<span data-ttu-id="7981a-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-552">String</span></span>|  
|<span data-ttu-id="7981a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-553">TABLE_TYPE</span></span>|<span data-ttu-id="7981a-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-554">String</span></span>|  
|<span data-ttu-id="7981a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-555">TABLE_GUID</span></span>|<span data-ttu-id="7981a-556">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-556">Guid</span></span>|  
|<span data-ttu-id="7981a-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-557">DESCRIPTION</span></span>|<span data-ttu-id="7981a-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-558">String</span></span>|  
|<span data-ttu-id="7981a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-559">TABLE_PROPID</span></span>|<span data-ttu-id="7981a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-560">Int64</span></span>|  
|<span data-ttu-id="7981a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-561">DATE_CREATED</span></span>|<span data-ttu-id="7981a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-562">DateTime</span></span>|  
|<span data-ttu-id="7981a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7981a-565">Columns</span><span class="sxs-lookup"><span data-stu-id="7981a-565">Columns</span></span>  
  
|<span data-ttu-id="7981a-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-566">ColumnName</span></span>|<span data-ttu-id="7981a-567">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-569">String</span></span>|  
|<span data-ttu-id="7981a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-571">String</span></span>|  
|<span data-ttu-id="7981a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-572">TABLE_NAME</span></span>|<span data-ttu-id="7981a-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-573">String</span></span>|  
|<span data-ttu-id="7981a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-574">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-575">String</span></span>|  
|<span data-ttu-id="7981a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-576">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-577">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-577">Guid</span></span>|  
|<span data-ttu-id="7981a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-579">Int64</span></span>|  
|<span data-ttu-id="7981a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-581">Int64</span></span>|  
|<span data-ttu-id="7981a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7981a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-583">Boolean</span></span>|  
|<span data-ttu-id="7981a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7981a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7981a-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-585">String</span></span>|  
|<span data-ttu-id="7981a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7981a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="7981a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-587">Int64</span></span>|  
|<span data-ttu-id="7981a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-588">IS_NULLABLE</span></span>|<span data-ttu-id="7981a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-589">Boolean</span></span>|  
|<span data-ttu-id="7981a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-590">DATA_TYPE</span></span>|<span data-ttu-id="7981a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-591">Int32</span></span>|  
|<span data-ttu-id="7981a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-592">TYPE_GUID</span></span>|<span data-ttu-id="7981a-593">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-593">Guid</span></span>|  
|<span data-ttu-id="7981a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7981a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-595">Int64</span></span>|  
|<span data-ttu-id="7981a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7981a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7981a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-597">Int64</span></span>|  
|<span data-ttu-id="7981a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7981a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-599">Int32</span></span>|  
|<span data-ttu-id="7981a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7981a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="7981a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-601">Int16</span></span>|  
|<span data-ttu-id="7981a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7981a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="7981a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-603">Int64</span></span>|  
|<span data-ttu-id="7981a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7981a-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-605">String</span></span>|  
|<span data-ttu-id="7981a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7981a-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-607">String</span></span>|  
|<span data-ttu-id="7981a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7981a-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-609">String</span></span>|  
|<span data-ttu-id="7981a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="7981a-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-611">String</span></span>|  
|<span data-ttu-id="7981a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7981a-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-613">String</span></span>|  
|<span data-ttu-id="7981a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-614">COLLATION_NAME</span></span>|<span data-ttu-id="7981a-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-615">String</span></span>|  
|<span data-ttu-id="7981a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7981a-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-617">String</span></span>|  
|<span data-ttu-id="7981a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7981a-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-619">String</span></span>|  
|<span data-ttu-id="7981a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="7981a-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-621">String</span></span>|  
|<span data-ttu-id="7981a-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-622">DESCRIPTION</span></span>|<span data-ttu-id="7981a-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7981a-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7981a-624">Procedures</span></span>  
  
|<span data-ttu-id="7981a-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-625">ColumnName</span></span>|<span data-ttu-id="7981a-626">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7981a-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-628">String</span></span>|  
|<span data-ttu-id="7981a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7981a-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-630">String</span></span>|  
|<span data-ttu-id="7981a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="7981a-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-632">String</span></span>|  
|<span data-ttu-id="7981a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7981a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-634">Int16</span></span>|  
|<span data-ttu-id="7981a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7981a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7981a-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-636">String</span></span>|  
|<span data-ttu-id="7981a-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-637">DESCRIPTION</span></span>|<span data-ttu-id="7981a-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-638">String</span></span>|  
|<span data-ttu-id="7981a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-639">DATE_CREATED</span></span>|<span data-ttu-id="7981a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-640">DateTime</span></span>|  
|<span data-ttu-id="7981a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7981a-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7981a-643">Views</span></span>  
  
|<span data-ttu-id="7981a-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-644">ColumnName</span></span>|<span data-ttu-id="7981a-645">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-647">String</span></span>|  
|<span data-ttu-id="7981a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-649">String</span></span>|  
|<span data-ttu-id="7981a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-650">TABLE_NAME</span></span>|<span data-ttu-id="7981a-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-651">String</span></span>|  
|<span data-ttu-id="7981a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7981a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="7981a-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-653">String</span></span>|  
|<span data-ttu-id="7981a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-654">CHECK_OPTION</span></span>|<span data-ttu-id="7981a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-655">Boolean</span></span>|  
|<span data-ttu-id="7981a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7981a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="7981a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-657">Boolean</span></span>|  
|<span data-ttu-id="7981a-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7981a-658">DESCRIPTION</span></span>|<span data-ttu-id="7981a-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-659">String</span></span>|  
|<span data-ttu-id="7981a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7981a-660">DATE_CREATED</span></span>|<span data-ttu-id="7981a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-661">DateTime</span></span>|  
|<span data-ttu-id="7981a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7981a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="7981a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="7981a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7981a-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="7981a-664">Indexes</span></span>  
  
|<span data-ttu-id="7981a-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7981a-665">ColumnName</span></span>|<span data-ttu-id="7981a-666">DataType</span><span class="sxs-lookup"><span data-stu-id="7981a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7981a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="7981a-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-668">String</span></span>|  
|<span data-ttu-id="7981a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="7981a-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-670">String</span></span>|  
|<span data-ttu-id="7981a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-671">TABLE_NAME</span></span>|<span data-ttu-id="7981a-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-672">String</span></span>|  
|<span data-ttu-id="7981a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7981a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="7981a-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-674">String</span></span>|  
|<span data-ttu-id="7981a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7981a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="7981a-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-676">String</span></span>|  
|<span data-ttu-id="7981a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-677">INDEX_NAME</span></span>|<span data-ttu-id="7981a-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-678">String</span></span>|  
|<span data-ttu-id="7981a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7981a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="7981a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-680">Boolean</span></span>|  
|<span data-ttu-id="7981a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7981a-681">UNIQUE</span></span>|<span data-ttu-id="7981a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-682">Boolean</span></span>|  
|<span data-ttu-id="7981a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7981a-683">CLUSTERED</span></span>|<span data-ttu-id="7981a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-684">Boolean</span></span>|  
|<span data-ttu-id="7981a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="7981a-685">TYPE</span></span>|<span data-ttu-id="7981a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-686">Int32</span></span>|  
|<span data-ttu-id="7981a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7981a-687">FILL_FACTOR</span></span>|<span data-ttu-id="7981a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-688">Int32</span></span>|  
|<span data-ttu-id="7981a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7981a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="7981a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-690">Int32</span></span>|  
|<span data-ttu-id="7981a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="7981a-691">NULLS</span></span>|<span data-ttu-id="7981a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-692">Int32</span></span>|  
|<span data-ttu-id="7981a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7981a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7981a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-694">Boolean</span></span>|  
|<span data-ttu-id="7981a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7981a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="7981a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="7981a-696">Boolean</span></span>|  
|<span data-ttu-id="7981a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-697">NULL_COLLATION</span></span>|<span data-ttu-id="7981a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-698">Int32</span></span>|  
|<span data-ttu-id="7981a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7981a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="7981a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-700">Int64</span></span>|  
|<span data-ttu-id="7981a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7981a-701">COLUMN_NAME</span></span>|<span data-ttu-id="7981a-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-702">String</span></span>|  
|<span data-ttu-id="7981a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7981a-703">COLUMN_GUID</span></span>|<span data-ttu-id="7981a-704">Guid</span><span class="sxs-lookup"><span data-stu-id="7981a-704">Guid</span></span>|  
|<span data-ttu-id="7981a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7981a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="7981a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="7981a-706">Int64</span></span>|  
|<span data-ttu-id="7981a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7981a-707">COLLATION</span></span>|<span data-ttu-id="7981a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="7981a-708">Int16</span></span>|  
|<span data-ttu-id="7981a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7981a-709">CARDINALITY</span></span>|<span data-ttu-id="7981a-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="7981a-710">Decimal</span></span>|  
|<span data-ttu-id="7981a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="7981a-711">PAGES</span></span>|<span data-ttu-id="7981a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="7981a-712">Int32</span></span>|  
|<span data-ttu-id="7981a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7981a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="7981a-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7981a-714">String</span></span>|  
|<span data-ttu-id="7981a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7981a-715">INTEGRATED</span></span>|<span data-ttu-id="7981a-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7981a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7981a-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7981a-717">See also</span></span>
- [<span data-ttu-id="7981a-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7981a-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
