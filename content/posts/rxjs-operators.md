+++
date = '2025-01-22T01:09:56+01:00'
draft = false
title = 'RxJs Operators'
categories = ['angular', 'rxjs']
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
* throttleTime
* debounceTime
* groupBy
* interval
* filter
* map
* startWith
* takeUntil
* takeUntilDestroyed


`throttleTime` or `debounceTime`, think about it like this: if the action is non-repetitive (like clicks, subsequent clicks perform the exact same action), then throttle, if it is repetitive (like typing, more keys hit means a different search qurery), use debounce