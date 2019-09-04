There is an export import syntax for legacy modules, and a standard export format for modern ES6 modules:

    // export the default export of a legacy (`export =`) module
    export import MessageBase = require('./message-base');

    // export the default export of a modern (`export default`) module
    export { default as MessageBase } from './message-base';

    // export an interface from a legacy module
    import Types = require('./message-types');
    export type IMessage = Types.IMessage;

    // export an interface from a modern module
    export { IMessage } from './message-types';