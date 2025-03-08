This does not compile - Error at run()
```txt
error[E0277]: the trait bound `Engine<HistoricalClock, EngineState<DefaultMarketData, DefaultStrategyState, DefaultRiskManagerState>, MultiExchangeTxMap<UnboundedTx<ExecutionRequest>>, DefaultStrategy<EngineState<DefaultMarketData, DefaultStrategyState, DefaultRiskManagerState>>, DefaultRiskManager<_>>: Processor<barter_data::streams::reconnect::Event<barter_instrument::exchange::ExchangeId, Result<MarketEvent<CustomInstrumentKey, CustomDataKind>, DataError>>>` is not satisfied
   --> src/main.rs:169:13
    |
167 |         let shutdown_audit = run(
    |                              --- required by a bound introduced by this call
168 |             &mut feed_rx,
169 |             &mut engine,
    |             ^^^^^^^^^^^ unsatisfied trait bound
    |
    = help: the trait `Processor<barter_data::streams::reconnect::Event<barter_instrument::exchange::ExchangeId, Result<MarketEvent<CustomInstrumentKey, CustomDataKind>, DataError>>>` is not implemented for `Engine<_, _, _, _, DefaultRiskManager<_>>`
            but trait `Processor<EngineEvent<DataKind>>` is implemented for `Engine<_, _, _, _, DefaultRiskManager<EngineState<DefaultMarketData, DefaultStrategyState, DefaultRiskManagerState>>>`
    = help: for that trait implementation, expected `EngineEvent<DataKind>`, found `barter_data::streams::reconnect::Event<barter_instrument::exchange::ExchangeId, Result<MarketEvent<CustomInstrumentKey, CustomDataKind>, DataError>>`
note: required by a bound in `run`
   --> /home/f1/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/barter-0.10.0/src/engine/mod.rs:87:1

For more information about this error, try `rustc --explain E0277`.
warning: `barter_project` (bin "barter_project") generated 5 warnings
error: could not compile `barter_project` (bin "barter_project") due to 1 previous error; 5 warnings emitted
```
```
```
