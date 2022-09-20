<template>
    <div class="navbar bg-gray-200">
        <div class="flex-1">
            <a class="btn btn-ghost normal-case text-xl">daisyUI</a>
        </div>
        <div class="flex-none px-10">
            <div class="form-control px-10">
                <form id="search-box" action="#">
                    <label :data-state="state" for="search">
                        <input type="text" placeholder="Search" @click="state = 'open'" @blur="state='close'" />
                        <i class="fa fa-search" @click="true" aria-hidden="true"></i>
                    </label>
                </form>
            </div>
            <div class="dropdown dropdown-end">
                <label tabindex="0" class="btn btn-ghost btn-circle avatar">
                    <div class="w-10 rounded-full">
                        <img src="https://placeimg.com/80/80/people" />
                    </div>
                </label>
                <ul tabindex="0"
                    class="mt-3 p-2 shadow menu menu-compact dropdown-content bg-base-100 rounded-box w-52">
                    <li>
                        <a class="justify-between">
                            Profile
                            <span class="badge">New</span>
                        </a>
                    </li>
                    <li><a>Settings</a></li>
                    <li><a>Logout</a></li>
                </ul>
            </div>
        </div>

    </div>



</template>

<script>
export default {

    data() {
        return {
            state: "close"  
        }

    }
}
</script>

<style lang="scss">
@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css");

label {
    position: relative;
    display: inline-block;
    background-color: #fff;
    padding: 5px 12px;
    transition: all 1s ease;
    border-radius: 0;
    box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);

    &::after {
        content: "";
        display: block;
        height: 2px;
        width: 80%;
        background-color: #f0ad4e;
        transition: all 1s ease 0.5s;
    }

    input {
        transition: width 1s ease, opacity 0.5s ease 0.5s;
        opacity: 1;
        width: 180px;
        height: 25px;
        border: 0;
        outline: none;
        color: darken(#f0ad4e, 25);
    }

    i {
        position: absolute;
        top: 11px;
        right: 11px;
        color: #333;
        cursor: pointer;
    }

    &[data-state="close"] {
        border-radius: 30px;
        padding: 5px 5px;
        transition: all 1s ease;

        &::after {
            width: 0%;
            transition: all 0.3s ease;
        }

        i {
            pointer-events: none;
        }

        input {
            width: 28px;
            height: 25px;
            opacity: 0;
            cursor: pointer;
            transition: opacity 0.5s ease, width 1s ease;
            // -webkit-appearance: none;
        }
    }
}
</style>