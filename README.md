# JavaScript-Daily-coding-7-solution

function decode_cnt_no_zero(message) {

   let length = message.length

   if (length <=1) {
        return 1
    }

   if (length >=2) {
       var parsed = parseInt(message.substring(0,2),10)
        if (parsed >=0 && parsed <= 26) {
            return (decode_cnt_no_zero(message.substring(1,length)) 
            + decode_cnt_no_zero(message.substring(2, length)))
        }
        return decode_cnt_no_zero(message.substring(1, length))
    }
}
