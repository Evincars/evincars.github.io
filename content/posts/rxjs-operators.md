+++
date = '2025-01-22T01:09:56+01:00'
draft = false
title = 'RxJs Operators'
+++

RxJS used in Adam's code:
* pairwise
* distinctUntilChanged
* delay
* forkJoin
* lastValueFrom
* withLatestFrom
* combineLatest
* defer (hlavni chain v rxMethod hned emituje value [TabInvoiceAddressComponent], coz muze zpusobit problem, takze se bud musi ostatni operatory zanorit do vnitrni .pipe nebo pouzit defer) - Adam takhle zanoruje by default vsude
* race
* merge
* finalize
* fromEvent
* debounceTime
* groupBy
* interval
* filter
* map
* startWith
* takeUntil
* takeUntilDestroyed
